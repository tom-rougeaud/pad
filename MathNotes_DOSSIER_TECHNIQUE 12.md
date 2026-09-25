# MathNotes — dossier de reprise

> **À quoi sert ce document.** Il contient tout ce qu'une nouvelle conversation avec Claude doit
> savoir pour reprendre MathNotes sans que vous ayez à réexpliquer le projet : la mission, les
> contraintes, l'architecture, les règles à ne jamais enfreindre, les pièges déjà rencontrés, le
> système de design, la méthode de travail et la batterie de tests.
>
> Il décrit l'état du **25 septembre 2026**. Mettez-le à jour quand vous ajoutez une
> fonctionnalité majeure : c'est lui qui vieillira, pas le code.

---

## 0. Comment reprendre le projet en trois gestes

**Geste 1 — joignez deux fichiers à la conversation :** ce dossier, et `MathNotes_source.html`
(0,49 Mo, la version éditable). *Ne joignez pas* `MathNotes.html` (1,10 Mo) : plus de la moitié
n'est que la police mathématique encodée, sans intérêt pour l'édition.

**Geste 2 — collez cette amorce :**

```
Voici MathNotes, un éditeur de cours de maths pour le lycée professionnel, et son dossier
de reprise. Lis le dossier en entier avant toute chose : il contient les contraintes, les
invariants et la méthode de travail à suivre.

Travaille comme le dossier l'indique : repère par recherche ciblée, modifie par script de
remplacement avec assertion sur le nombre d'occurrences, jamais par réécriture du fichier.
Après chaque modification, relance la batterie de tests et montre-moi le résultat.

Ce que je veux faire aujourd'hui : […]
```

**Geste 3 — à la fin de la session,** demandez la version distribuable :
`python3 build.py dist MathNotes_source.html MathNotes.html`.

---

## 1. Le projet en une page

| | |
|---|---|
| **Quoi** | Un éditeur de cours de mathématiques, contenu dans **un seul fichier HTML**, sans installation ni compte. |
| **Pour qui** | Les professeurs de mathématiques en **lycée professionnel** : 3ᵉ Prépa-Métiers, CAP, Bac Pro. |
| **Auteur** | Tom Rougeaud, professeur de mathématiques. Hébergé sur GitHub Pages. |
| **Promesse 1** | Ce que l'on voit à l'écran est **exactement** ce qui s'imprime : mêmes couleurs, même découpage en pages, page pour page. |
| **Promesse 2** | Le contenu pédagogique est **déjà là** : 97 modèles de formules, chacun avec un exemple chiffré et une situation professionnelle. |
| **Promesse 3** | **Rien ne dépend du réseau.** Moteur mathématique et polices embarqués ; les pages web produites sont autonomes elles aussi. |
| **Promesse 4** | **Une ressource se génère sans jamais toucher au dessin.** L'application fabrique le prompt, contrôle la réponse — capacités, compétences, et jusqu'à l'arithmétique des corrections — puis dessine elle-même. |

### Chiffres actuels

13 chapitres · 97 modèles · 194 exemples · 278 formules au catalogue · 90 commandes `/` ·
16 blocs de ressource · 5 types de ressource · 3 parcours de différenciation ·
**programme embarqué : 6 niveaux, 28 thèmes, 86 chapitres, 507 items** ·
46 symboles `//` · 150 icônes en 7 familles · 5 compétences du Bac Pro · 35 fonctions de
tableur · 33 fiches de Tuto · 69 questions de FAQ · 473 fonctions JavaScript ·
**497 vérifications automatiques**.

---

## 2. Règles de collaboration

Ces règles viennent de l'auteur. Elles ne se discutent pas.

1. **Tout en français**, y compris les commentaires de code ajoutés et les messages de l'interface.
2. **Ne jamais citer Excel ni Canva**, même par comparaison. Dire « tableur », « fonctions de
   calcul », et décrire les comportements sans les rattacher à un produit.
3. **Ne rien livrer sans avoir testé.** L'auteur a explicitement demandé que tout soit vérifié
   plutôt qu'annoncé. Les mesures valent mieux que les affirmations.
4. **Ne pas altérer l'existant.** Chaque ajout doit laisser les 248 vérifications au vert.
5. **Signaler les limites** plutôt que de les masquer : ce qui ne marche pas, ce qui a un coût,
   ce qui reste à la charge de l'utilisateur.
6. Quand l'auteur demande une fonctionnalité, **confirmer la compréhension et proposer des
   options faciles à trancher** avant de construire, s'il s'agit d'un gros morceau.

---

## 3. Architecture du fichier

Un seul fichier, quatre couches successives :

```
<head>
  <!-- KATEX:DEBUT --> … <!-- KATEX:FIN -->   ← bloc fabriqué, ne pas éditer à la main
  <style> …  ~1 200 lignes de CSS
<body>
  … ~1 200 lignes de balisage : bandeau, ruban, barre de symboles, rail,
    éditeur, panneau latéral, pages Tuto/Contact/Confidentialité, fenêtres
  <script> … ~4 900 lignes de JavaScript
```

### Repères de recherche

Le fichier ne se lit pas en entier : on y **cherche**. Les sections sont balisées par des
commentaires `/* ── NOM ── */`. Repères utiles, dans l'ordre du fichier :

| Sujet | Chercher |
|---|---|
| Palette et variables | `/* ── TOKENS ──` |
| Éditeur, page A4 | `/* ── EDITOR — A4` |
| Encadrés, zones colorées | `CALLOUTS`, `CUSTOM COLOUR ZONE` |
| Exercices | `EXERCISE BLOCK`, `function insExo` |
| **QCM** | `/* ── QCM ─`, `function insQCM`, `function qcmQuestionHTML` |
| Formules (affichage) | `function kx(`, `function mkMX`, `function mkMD` |
| Formules (interaction) | `Selection: 1 click selects` |
| Images | `/* ── Image`, `function shrinkImage`, `function loadIF` |
| Tableaux | `function confirmTbl`, `function tblAddCol` |
| Tableur | `SPREADSHEET`, `function buildSheet`, `function evalF`, `XFDEF` |
| Catalogue de formules | `const SC=[`, `const DS=[`, `const TPLS={` |
| Exemples des modèles | `function insertExample`, `function exBlocks` |
| **Pagination** | `function paginateCore` |
| **Impression** | `@media print{` (le grand bloc, vers la ligne 803) et `function preparePrint` |
| **Export web** | `function cleanHTML`, `function exportWeb`, `EXPORT_KEEP`, `EXPORT_DROP` |
| **Stockage** | `function lsSet`, `function saveDoc`, `function docKey` |
| **Bibliothèque** | `BIBLIOTHÈQUE DE COURS`, `function libInit`, `function renderLib` |
| **Verrou d'onglets** | `VERROU ENTRE ONGLETS`, `function startTabLock` |
| Feuille blanche | `function blankSheet`, `function restoreBackup` |
| Historique | `function pushHist`, `function pushHistNow`, `function doUndo` |
| Tuto et FAQ | `id="page-tuto"`, `class="acc faq"` |
| Démarrage | `/* ── INIT ──` |

**Programme** : `REF_DEFAUT` (le programme de l'auteur, embarqué), `refConvertir`
(accepte le fichier de progression brut et l'ancien format plat), `refItemsChapitre` et
`refItem` (les codes d'item, « pm0m1 » → « pm0m1-3 »), `RF_SEL` et `rfRendu` (l'arbre
pliable, la recherche, la sélection à travers plusieurs niveaux), `ASSISTANTS`.

**Atelier de ressources** : `MNR_BLOCS` et `MNR_TYPES` (le vocabulaire, source unique),
`mnrCompile` / `mnrBloc` (la traduction), `mnrGarde` (les trois parcours), `mnrAudit`
(le contrôle qualité), `mnrEgalitesFausses` et `mnrEval` (l'arithmétique refaite),
`mnrOrphelins` (les nombres sans origine), `mnrPrompt` (le prompt), `REF` et
`mnrCapacitesConnues` (le programme officiel), `openAtelier` / `mnrImporter` (la fenêtre).

**Pagination et compétences** : `paginateCore` (tout le calcul, réutilisé tel quel par
l'export), `secable` / `coupure` / `decouper` / `pageAremplir` (coupure d'un paragraphe),
`pageOp` et `rebuildFromGroups` (outils de page), `COMPETENCES` et `insCompetence`
(pastilles du Bac Pro).

### Structures de données

| Nom | Contenu |
|---|---|
| `SC` | Commandes `/`. `{c, cat, tags, l}` où `l` est le LaTeX. Entrées d'action : `{…, l:'', special:'qcm', prevTxt:'…'}`. |
| `DS` | Symboles `//`. `{s, l, cmd}`. |
| `TPLS` | Catalogue des modèles : `{'Chapitre':[{name, lls, ex, exc}]}`. `lls` = formules, `ex` = exemple chiffré, `exc` = situation professionnelle. **Bloc généré — voir §8.** |
| `TPL_CHAP_KW` | Mots-clés par chapitre, pour la recherche. Généré avec `TPLS`. |
| `ICON_SETS` | 7 familles d'icônes, en JSON. |
| `XFDEF` | 35 fonctions de tableur, `['NOM','Description']`. |
| `CZ_COLORS` | 8 teintes des zones colorées : `{k, n, bg, bd}`. |
| `LIB` | `{cur:'id', docs:[{id,title,updated,size}]}`. **Métadonnées seulement** : le contenu vit dans la base locale (voir §3 bis). |
| `DOC_CACHE` | Contenu des cours en mémoire, par identifiant. Toujours à jour avant l'écriture disque. |
| `SHEETS` | Données vivantes des tableurs, par identifiant. |

### Où vivent les données

**Deux espaces, et c'est volontaire.**

| Espace | Ce qu'il contient | Pourquoi |
|---|---|---|
| **Base locale** (IndexedDB, base `mathnotes`, magasin `docs`) | Le contenu des cours, par identifiant, plus la copie de secours sous `__backup__`. | Quota de plusieurs centaines de mégaoctets, suivant l'espace disque libre. |
| **Espace clé-valeur** (localStorage) | `mn_lib` · `mn_title` · `mn_title_manual` · `mn_cfg` · `mn_backup_title` / `mn_backup_at` · `mn_lock_<id>` | Minuscule, et **lu de façon synchrone** par tout le programme. |

L'accès au contenu passe par quatre fonctions : `docPut(id, body)`, `docGet(id)`, `docDel(id)`,
`dbRaw(id)` (lecture brute, sans repli ni cache). Toutes renvoient une promesse.

**Repli automatique.** Si la base locale est indisponible — certains modes privés, stockage
bloqué — `docPut`/`docGet` retombent sur `mn_doc_<id>` dans l'espace clé-valeur, avec son plafond
de 5 Mo et son bandeau d'alerte. Le reste du programme ne voit aucune différence.

**Reprise des anciens cours** (`docMigrate`, au démarrage), avec deux garde-fous :
1. Si la base contient **déjà** ce cours, la copie de l'ancien emplacement est un reliquat :
   elle est supprimée sans rien écraser.
2. Sinon le cours est écrit, **relu, comparé à l'original**, et l'ancienne copie n'est effacée
   qu'après cette vérification.

---

## 4. Les quatorze invariants

Casser l'un d'eux, c'est casser le produit. Chacun est couvert par au moins un test.

1. **Un seul fichier.** Aucune dépendance à installer, aucun cadriciel, aucune compilation pour
   éditer. Le seul artefact fabriqué est le bloc KaTeX.
2. **Écran = papier.** Aucune règle d'impression ne doit repeindre un bloc d'une autre teinte que
   celle de l'écran. `print_audit.py` compare élément par élément.
3. **Rien de l'interface sur le papier.** Boutons, pastilles de couleur, badges, poignées :
   tout doit disparaître à l'impression. L'impression fonctionne en **liste blanche**
   (`body>*:not(#layout)` …), pas en liste noire : un élément d'interface ajouté plus tard est
   masqué d'office, mais son *contenu* dans l'éditeur doit être masqué explicitement.
4. **Rien ne s'écrit dans le blanc entre deux pages.** Trois régimes, et un seul est
   automatique :
   - un **bloc indivisible** (encadré, tableau, image, formule, exercice) passe **entier** sur la
     page suivante ;
   - un **QCM** se coupe **entre deux questions** — jamais entre une question et ses réponses ;
   - un **paragraphe de texte** plus haut que la page se **poursuit page suivante**, la coupure
     tombant entre deux mots (`secable`, `coupure`, `decouper` dans `paginateCore`).

   La garantie à tester n'est pas « le bloc n'est pas coupé » mais « **aucun rectangle de ligne
   ne dépasse la limite basse de sa page** » : c'est ce que vérifie `pg_test.py`.
5. **Page 1 à l'écran = page 1 du PDF.** Vérifié par `pdf_test.py` sur un document repère.
6. **Les styles de l'export dérivent de ceux de l'éditeur** (`buildExportCSS` parcourt la feuille
   interne et réécrit `#editor` en `.mn-sheet`). Ne jamais écrire un style d'export à la main :
   l'écran et l'export divergeraient. Deux filtres pilotent cela : `EXPORT_KEEP` (ce qui est
   repris) et `EXPORT_DROP` (ce qui est écarté). **Toute nouvelle famille de classes doit être
   ajoutée à `EXPORT_KEEP`**, et ses boutons d'édition à `EXPORT_DROP`.
7. **Toute écriture passe par la bonne porte.** Le contenu d'un cours par `docPut`, les
   métadonnées par `lsSet`. Jamais `localStorage.setItem` en direct : une écriture qui échoue
   doit lever le bandeau rouge, pas disparaître.
   **Corollaire : ne jamais détruire avant d'avoir relu.** C'est la règle de `docMigrate`.
8. **Le LaTeX du catalogue est encodé en JSON**, jamais tapé à la main dans le fichier (§8).
9. **Chaque exemple se comprend seul** : toutes ses données énoncées, chaque résultat calculé.
   `exc_audit.py` refuse tout nombre orphelin.
10. **Les blocs imbriqués sont scellés.** Le conteneur porte `contenteditable="false"`, seuls les
    champs internes sont modifiables. Une zone colorée ne s'imbrique jamais dans une autre
    (`noNest`), et une image ne va pas dans une zone colorée.
11. **Le curseur appartient à son hôte.** Ne jamais appeler `ED.focus()` : utiliser `editHost()`
    et `restoreSR()`, sinon le curseur saute hors des blocs imbriqués.
13. **Le modèle de langage n'écrit jamais de HTML.** Une ressource générée décrit une
    leçon — `{"b":"definition","t":"…"}` — jamais une page. `mnrCompile` la traduit avec les
    mêmes fabriques que le ruban. Toute envie d'enrichir le format se règle en ajoutant une
    ligne à `MNR_BLOCS`, **jamais** en laissant passer du HTML dans un champ de texte.
14. **Le prompt est fabriqué, jamais écrit à la main.** `mnrPrompt` construit la section du
    vocabulaire à partir de `MNR_BLOCS` et l'extrait du programme à partir de `REF`. Le prompt
    et le compilateur ne peuvent donc pas se contredire. Un prompt recopié dans un fichier
    dormirait et vieillirait : il n'en existe aucun.

12. **Une opération de page ne fige que ce qu'elle crée.** `rebuildFromGroups` ne pose un
    `.pg-manual` que pour une page **vierge insérée** ou **dupliquée** (`fixe:true`) et pour les
    sauts que l'utilisateur avait lui-même posés (`pgInfo.manuelles`). Poser un saut à chaque
    frontière fige le document pour toujours : plus rien ne remonte quand on efface du texte.

---

## 5. Les pièges déjà rencontrés

Chacun a coûté du temps. Ils sont listés pour ne pas les repayer.

| Piège | Ce qui se passe | Parade |
|---|---|---|
| **`\t` et `\f` en JavaScript** | `'\frac'` dans une chaîne JS devient un saut de page suivi de `rac` : la formule ne s'affiche plus. C'est ce qui avait cassé `/tva` et dix autres formules. | Le catalogue est généré par `json.dumps` (§8). `catalog_test.py` rend **toutes** les formules à chaque fois. |
| **`%` en LaTeX** | `%` ouvre un commentaire : la fin de la ligne disparaît. | `sanitizeLatex()` échappe `% # & $`, sans double-échapper. |
| **`data-bound` sérialisé** | Le marqueur « écouteur déjà posé » partait dans la sauvegarde ; au rechargement, plus rien n'était rebranché. | `cleanHTML` retire tous les `[data-bound]`. |
| **`querySelectorAll` n'inclut pas l'élément lui-même** | `bindQcm(blk)` ne trouvait rien quand `blk` **était** le bloc. | Tester `root.classList.contains(...)` avant de descendre. |
| **`</script>` dans du JS intégré** | Termine la balise prématurément. | `build.py` vérifie ; l'export échappe avec `<\/script`. |
| **Apostrophe dans un gabarit de chaîne** | `\'` écrit dans un `template literal` devient `'` à l'exécution : erreur de syntaxe dans la page produite. | Éviter les apostrophes échappées dans le code de l'export. |
| **Espace du navigateur saturé** | `localStorage.setItem` lève une erreur non capturée depuis un minuteur : l'utilisateur croit son cours enregistré. | Invariant 7 + `lib_test.py`. |
| **Historique différé** | `pushHist` attend 120 ms : une action destructrice enchaînée efface l'état d'avant. | `pushHistNow()` avant toute suppression. |
| **Boucle sur une fonction devenue asynchrone** | `while(LIB.docs.length>1){ libAskDel(...) }` ne termine jamais : la liste ne diminue pas dans le tour de boucle. | Après le passage au stockage large, `libOpen`, `libNew`, `libDup`, `libAskDel`, `libSwitchTo`, `takeOver`, `restoreBackup` et `loadDoc` sont **asynchrones** : tout appel en boucle doit être attendu. |
| **Ancienne copie qui écrase la récente** | Une reprise relancée réécrivait par-dessus une version plus neuve. | `dbRaw` vérifie d'abord si le cours est déjà en base. |
| **`buildExportCSS` et KaTeX** | Sans exclusion, l'export réécrivait les ~1 000 règles de KaTeX. | La feuille `#katex-style` est exclue explicitement. |
| **Fonds non imprimés** | L'option « Graphiques d'arrière-plan » du navigateur est décochée par défaut. | Chaque encadré porte **aussi** un contour de sa couleur : une bordure s'imprime toujours. |
| **Mise en page qui bouge à l'impression** | Le rail restait affiché et rétrécissait la colonne de texte : les paragraphes se reformaient. | Liste blanche d'impression (invariant 3). |
| **KaTeX absent aux tests** | Sans KaTeX, les tests validaient un rendu de repli, donc rien. | `harness.py` sert KaTeX depuis `node_modules`. |
| **Deux espaceurs qui se suivent** | `decouper` est appelé deux fois par tour (avant et après le déplacement du bloc). La seconde fois repartait de la première page et reposait un espaceur là où c'était déjà coupé : haut de zéro pixel, invisible à l'écran, mais **deux coupures consécutives à l'impression, donc une page blanche**. | `pageAremplir()` repart de la dernière coupure posée, et un espaceur qui repousse moins de 2 px est retiré. Le test compare le nombre de pages écran et PDF. |
| **`normalize()` et le curseur** | Retirer les espaceurs recolle des nœuds de texte à chaque mise en page. | Le navigateur déplace les `Range` vivants avec eux ; le test §2 de `pg_test.py` tape dans un paragraphe coupé et vérifie que rien ne se perd. |
| **Écriture non atomique d'un patch** | `open(P,'w')` tronque le fichier *avant* d'écrire : une erreur d'encodage en plein milieu laisse un `MathNotes.html` vide. | Tous les scripts de patch écrivent dans `P + '.tmp'` puis `os.replace`. Le fichier n'est jamais dans un état intermédiaire. |
| **Substituts Unicode en Python** | `'\ud83d\udcd8'` dans une chaîne Python non brute produit un substitut isolé, inencodable en UTF-8. | Écrire l'émoji tel quel (📘) dans les scripts de patch, ou passer par une chaîne brute. |
| **Tentation d'accepter du HTML** | Un modèle glisse parfois une balise dans un champ de texte « pour bien faire ». Si on la laisse passer, la charte dérive et l'invariant 13 tombe. | `mnrRich` échappe tout : `esc()` sur chaque morceau, et seuls `**`, `*`, `$…$`, `{comp}` et `[comp]` sont interprétés. |
| **`eval` pour vérifier un calcul** | Le fichier importé vient de l'extérieur : lui donner `eval` ou `Function` serait lui donner les clés de la page. | `mnrEval` est un analyseur descendant de vingt-cinq lignes : `+ − × ÷` et parenthèses, rien d'autre. |
| **Faux positifs du vérificateur de calculs** | `t = \frac{V_f - V_i}{V_i} \times 100` est une formule littérale, pas une égalité numérique. | `mnrEval` renvoie `null` dès qu'une lettre reste après normalisation : l'égalité est alors ignorée, jamais signalée. Le contrôle est volontairement prudent. |
| **Caractère sans rectangle** | `getBoundingClientRect()` d'une plage d'un seul caractère est vide pour l'espace en fin de ligne : la recherche dichotomique partait du mauvais côté. | `basDe` renvoie `NaN`, `basSur` décale de quelques caractères plutôt que de renoncer. |

---

## 6. Système de design

### Couleurs (`:root`, section TOKENS)

| Rôle | Valeur |
|---|---|
| Fond de page / carte / papier | `#F2EDE3` · `#FFFFFF` |
| Texte principal / secondaire | `#1A1A2E` · `#6B7280` |
| Accent (bleu) | `#2F80ED` |
| Vert | `#27AE60` — favicon des exports, validations |
| Violet | `#7C3AED` — théorèmes, FAQ |
| Orange | `#D97706` / `#B45309` — exemples, corrections de QCM, alertes douces |
| Turquoise | `#0D9488` — QCM, situations professionnelles |
| Indigo | `--indigo` — exercices |
| Rouge | `#DC2626` / `#B91C1C` — suppressions, alerte de sauvegarde |

Trois thèmes : clair, sombre (`[data-theme=dark]`), sépia. **Toute nouvelle couleur doit avoir sa
variante sombre**, sinon elle devient illisible.

### Typographie

DM Sans (interface et corps), DM Mono (code, monospace), Lora (titres de documents). Chargées
depuis Google Fonts avec repli sur les polices du système. La taille de base est la variable
`--fs`, réglable par l'utilisateur.

### Conventions visuelles

- Blocs de contenu : `border-radius:10px`, `border-left:4px solid <couleur du bloc>`, fond à
  6–13 % d'opacité de la même couleur.
- Boutons d'action : `border-radius:6-8px`, `font-size:11-13px`, `font-weight:600-700`.
- Chaque bouton porte un `title` en français — ils servent d'étiquettes d'accessibilité.
- Les messages transitoires passent par `showToast()`, ceux qui offrent une action par
  `showToastAction()`. Les alertes persistantes sont des bandeaux fixes en haut au centre.

---

## 7. Méthode de travail

C'est la partie la plus importante du dossier. **Un fichier de 7 000 lignes ne se réécrit pas.**

### La règle

1. **Repérer** par recherche ciblée (`grep`), jamais en lisant tout le fichier.
2. **Modifier** par script Python de remplacement, avec **assertion sur le nombre d'occurrences** :

```python
def sub(old, new, label):
    c = src.count(old)
    if c != 1:
        sys.exit('%s (%d) : %s' % ('INTROUVABLE' if c == 0 else 'AMBIGU', c, label))
    src = src.replace(old, new)
    print('ok ·', label)
```

Un remplacement qui n'a pas exactement une cible **arrête tout** : on ne modifie jamais à
l'aveugle, et on ne touche jamais deux endroits en croyant n'en toucher qu'un.

3. **Vérifier** : `check_calls.py`, ESLint, puis la batterie de tests.
4. **Regarder** : pour tout changement visuel, produire une capture ou un PDF et l'examiner.
   Plusieurs défauts n'ont été trouvés que par l'image.

### Ce qu'il ne faut pas faire

- Réécrire le fichier entier ou une grande section « au propre ».
- Ajouter une syntaxe récente (`?.`, `??`, `:has()`, `structuredClone`, `.at()`) : la
  compatibilité avec les navigateurs anciens des établissements est un choix assumé.
- Écrire du LaTeX directement dans le fichier (§8).
- Ajouter une classe sans se demander si elle doit figurer dans `EXPORT_KEEP` ou `EXPORT_DROP`.

---

## 8. Chaîne d'outils

| Fichier | Rôle |
|---|---|
| `build.py` | `source` retire KaTeX (0,49 Mo, éditable) · `dist` l'intègre (1,10 Mo, publiable). Aller-retour exact. |
| `tpl_a.py` · `tpl_b.py` | **Source du catalogue de modèles.** Chapitres classiques et chapitres professionnels. |
| `gen_tpls.py` | Régénère `TPLS` et `TPL_CHAP_KW` dans le fichier, **par encodage JSON** : aucun antislash ne peut être mal échappé. |
| `harness.py` | Banc d'essai Playwright : ouvre l'application, sert KaTeX en local, bloque le reste du réseau. |
| `check_calls.py` | Détecte les `onclick="fonctionInexistante()"`. |
| `.eslintrc.json` | `no-undef`, `no-redeclare`, `no-dupe-keys`. |
| `build_guide.py` · `guide_pdf.py` | Guide complet, **extrait du Tuto de l'application** : il ne peut pas diverger. |
| `presentation.html` · `pres_pdf.py` | Présentation 2 pages : la page web **est** la source, son impression produit le PDF. |

### Modifier le catalogue de modèles

```bash
# 1. éditer tpl_a.py (chapitres classiques) ou tpl_b.py (commerce, prix, finance)
# 2. régénérer le bloc TPLS dans le fichier
python3 gen_tpls.py
# 3. vérifier que tout se rend et qu'aucun exemple n'a de donnée orpheline
python3 catalog_test.py && python3 exc_audit.py
```

Format d'un modèle : `(nom, [formules LaTeX], [lignes d'exemple], [lignes de situation pro])`.
Dans les lignes, `$…$` est une formule en ligne, `**…**` du gras, et une ligne entièrement
encadrée par `$$…$$` devient une formule en bloc.

### Installer l'environnement de test

```bash
npm install katex@0.16.9 @fontsource/dm-sans @fontsource/dm-mono @fontsource/lora
pip install playwright beautifulsoup4
```

---

## 9. Batterie de tests — 497 vérifications

```bash
for t in catalog_test exc_audit ex_test qcm_test qcm2_test regress_test \
         pdf_test qcm_pdf_test lib_test img2_test safety_test offline_test \
         tablet_test idb_test leak_test fmt_test comp_test pg_test mnr_test \
         demo_atelier print_audit; do
  printf '%-16s ' $t; python3 $t.py 2>&1 | tail -1
done
```

Avant toute exécution, régénérer et relire le JavaScript :

```bash
python3 extract_js.py && node --check _app.js \
  && npx eslint --no-eslintrc -c .eslintrc.json _app.js \
  && python3 check_calls.py
```

| Suite | Ce qu'elle protège |
|---|---|
| `catalog_test` | Les 278 formules et 194 exemples se rendent tous |
| `exc_audit` | Aucun exemple ne contient de donnée orpheline |
| `ex_test` (14) | Insertion des exemples, pas d'imbrication de zones |
| `qcm_test` (56) | QCM : création, édition, correction, impression, export interactif |
| `qcm2_test` (36) | Correction par question, corbeille, coupure de page, vérification en orange |
| `regress_test` (26) | Ruban, formules, tableaux, tableur, exercices, pagination, réouverture |
| `pdf_test` (13) | Page écran = page PDF, versions élève et professeur |
| `qcm_pdf_test` (13) | QCM long : chaque question avec ses réponses sur la même page |
| `lib_test` (24) | Bibliothèque de cours et alerte de sauvegarde |
| `img2_test` (11) | Réduction des images, transparence |
| `safety_test` (23) | Feuille blanche réversible, verrou entre onglets |
| `offline_test` (11) | Application **et exports** vérifiés réseau totalement coupé |
| `tablet_test` (21) | Écrans étroits, sans rien changer au-dessus de 1100 px |
| `idb_test` (22) | Stockage large : capacité, persistance après rechargement, reprise vérifiée, repli, 30 photos dans un cours |
| `leak_test` (9) | Aucune écriture qui s'accumule : la place occupée suit la somme des cours |
| `fmt_test` (13) | Jauge de stockage : unités, virgule française, formulation |
| `comp_test` (23) | Pastilles de compétences : insertion, effacement, taille, couleurs, impression, export |
| `pg_test` (39) | Un long paragraphe se poursuit page suivante ; aucune ligne dans le blanc ; les outils de page ne figent rien ; écran = PDF |
| `mnr_test` (122) | Atelier : chaque bloc produit son objet, les trois parcours sortent d'une source, chaque classe de défaut est arrêtée, le prompt contient ce qu'il doit, son exemple est lui-même valide, l'import va jusqu'au document |
| `demo_atelier` (21) | La boucle complète sur une ressource réelle : programme → prompt → ressource → contrôle → trois parcours → PDF |
| `print_audit` | Écran et impression comparés élément par élément |

**Toute nouvelle fonctionnalité doit arriver avec sa suite de tests.** C'est ce qui a permis
d'enchaîner une vingtaine de sessions sans régression.

---

## 10. Dettes connues et feuille de route

### Limites assumées

- **Les réponses des QCM sont encodées, pas chiffrées** dans la page web exportée : un élève qui
  lirait le code source pourrait les retrouver. Documenté dans la FAQ ; pour un devoir noté, le
  PDF version élève est la bonne sortie.
- **Aucun `aria-label` ni `role`** : les 141 attributs `title` servent d'étiquettes. À reprendre
  si un usage avec lecteur d'écran se présente.
- **Trois fonctions mortes** : `insBlockSmart`, `getTextBeforeCaret`, `hasTitle`.
- **Le programme embarqué vient de l'auteur** (`CC BY-NC-SA 4.0 — © 2026 Tom Rougeaud`,
  tiré de son outil « Suivi de Progression »), pas d'une lecture des textes officiels par le
  modèle. Les références de BO sont celles qu'il a saisies. Il reste remplaçable et
  modifiable depuis l'onglet Programme.
- **Les items n'ont pas de code officiel** : le code `pm0m1-3` est fabriqué par l'application
  à partir de l'identifiant de chapitre et du rang. Il est stable tant que l'ordre des items
  ne bouge pas ; réordonner un chapitre décale les codes des ressources déjà écrites.
- **Le vérificateur de calculs ne lit que les égalités numériques.** Un raisonnement conduit
  en toutes lettres, une unité fausse ou un résultat juste mais hors sujet lui échappent.
  Il attrape l'étourderie d'arithmétique, pas l'erreur de pensée : la relecture reste due.
- **Déplacer une page** (`↑` `↓`) réordonne son **contenu**, pas ses frontières : sans saut
  figé, le texte se remet en page et les limites retombent quelques lignes plus loin. C'est le
  prix à payer pour que le document ne se fige jamais — et c'est le bon compromis, l'auteur
  ayant explicitement demandé que l'on puisse toujours faire remonter un bloc.
- **Les polices de l'interface** viennent encore de Google Fonts (repli système si absentes).
  Les polices mathématiques, elles, sont embarquées.
- **Téléphone** : l'application se charge et reste manipulable, mais la saisie longue n'y est pas
  confortable. La cible est l'ordinateur et la tablette.

### Pistes

- [ ] Barème et note chiffrée sur les QCM
- [ ] Version B d'un QCM, ordre des réponses mélangé
- [ ] Banque de situations professionnelles par filière
- [ ] Insertion de graphiques de fonctions
- [ ] Étiquettes d'accessibilité sur les boutons à icône
- [ ] Grille de compétences prête à remplir, construite depuis les pastilles
- [ ] Codes d'item indépendants du rang, pour survivre à un réordonnancement
- [ ] Mémoriser la dernière sélection d'items d'une séance à l'autre
- [ ] Un bouton « Produire les trois parcours » qui crée les trois documents d'un coup
- [ ] Recompiler une ressource déjà importée après une évolution de l'application

---

## 11. Repères historiques

Ce que l'auteur a explicitement demandé de retirer ou d'éviter, pour ne pas le réintroduire :

- **L'intégration de vidéos** : retirée, elle ne fonctionnait pas.
- **La fonction « Encadrer »** : retirée, trop instable.
- **L'icône du panneau d'icônes** doit être un **cahier** (📓), pas un visage souriant.
- **Le menu d'icônes** ne se ferme que par sa croix, jamais par un clic ailleurs.
- **Les images** ne vont pas dans une zone colorée — c'est volontaire, et expliqué dans la FAQ.
- **Un seul accès aux réglages** : les doublons de navigation ont été supprimés.

---

*Dossier établi le 25 septembre 2026, révisé après l'intégration du programme et de son arbre. À joindre à toute nouvelle conversation, avec
`MathNotes_source.html`.*
