<div align="center">

# Σ MathNotes

**Écrire, illustrer et évaluer un cours de mathématiques de lycée professionnel — dans un seul fichier.**

Un éditeur de cours qui met les formules à portée de clavier, propose 97 modèles prêts à l'emploi
avec leurs exemples, génère des QCM corrigés, et produit un PDF conforme au pixel près à ce que
vous voyez à l'écran. **Aucune connexion Internet n'est nécessaire.**

[![Fichier unique](https://img.shields.io/badge/fichier-unique-27AE60)](#)
[![Sans installation](https://img.shields.io/badge/installation-aucune-2F80ED)](#)
[![Hors ligne](https://img.shields.io/badge/fonctionne-hors%20ligne-0D9488)](#)
[![Public](https://img.shields.io/badge/public-3e%20Pr%C3%A9pa--M%C3%A9tiers%20%C2%B7%20CAP%20%C2%B7%20Bac%20Pro-7C3AED)](#)

</div>

---

## Sommaire

- [Pourquoi](#pourquoi)
- [Démarrage](#démarrage)
- [Fonctionnalités](#fonctionnalités)
- [Raccourcis](#raccourcis)
- [Bibliothèque de modèles](#bibliothèque-de-modèles)
- [Évaluer : exercices et QCM](#évaluer--exercices-et-qcm)
- [Distribuer : PDF et page web](#distribuer--pdf-et-page-web)
- [Vos cours et leur sécurité](#vos-cours-et-leur-sécurité)
- [Confidentialité](#confidentialité)
- [Sous le capot](#sous-le-capot)
- [Développement et tests](#développement-et-tests)
- [Feuille de route](#feuille-de-route)
- [Auteur](#auteur)
- [Licence](#licence)

---

## Pourquoi

Préparer un cours de maths oblige d'ordinaire à jongler entre trois outils : un traitement de
texte qui ne sait pas écrire les formules, un tableur pour les calculs, et un logiciel de mise en
page pour que l'ensemble soit lisible. Chaque aller-retour coûte du temps, et la mise en page
finit toujours par se décaler à l'impression.

MathNotes réunit les trois, avec trois partis pris :

1. **Ce que vous voyez est ce qui s'imprime.** La page à l'écran est une A4 paginée en temps
   réel. Mêmes couleurs, même découpage : jamais un tableau, une formule, un exercice ou une
   question de QCM coupés entre deux pages, et un long paragraphe qui se poursuit page suivante
   comme dans un traitement de texte.
2. **Le contenu est déjà là.** 97 modèles de formules, chacun accompagné d'une application
   chiffrée et d'une situation professionnelle, prêts à insérer et entièrement modifiables.
3. **Une ressource se génère sans jamais toucher au dessin.** L'application fabrique le
   prompt, contrôle la réponse — jusqu'à refaire l'arithmétique des corrections — puis dessine
   elle-même, dans sa charte.
4. **Rien ne dépend du réseau.** Le moteur mathématique et ses polices sont contenus dans le
   fichier : l'application fonctionne derrière un pare-feu d'établissement, et les pages web
   que vous produisez aussi.

---

## Démarrage

**En ligne** — ouvrez la page publiée du dépôt (GitHub Pages).

**En local** — téléchargez `MathNotes.html` et ouvrez-le dans votre navigateur. Il n'y a rien à
installer, ni compte à créer, ni connexion à établir.

Premiers gestes, dans l'ordre :

```
1. Écrivez trois lignes de cours.
2. Tapez  /tva   → la formule s'écrit toute seule.
3. Panneau de droite → onglet Modèles → 🏭 Situation pro.
4. Ruban → ☑️ QCM → cochez la bonne réponse.
5. Ruban → 🖨 Imprimer → Version élève ou Version professeur.
```

L'onglet **🎓 TUTO** de l'application contient 26 fiches et 54 questions fréquentes.

---

## Fonctionnalités

### ✍️ Rédaction

| | |
|---|---|
| **Ruban complet** | Gras, italique, souligné, titres, listes, citation, code, surligneur, couleurs, police et taille. Les raccourcis habituels d'un traitement de texte fonctionnent. |
| **Taille de police libre** | N'importe quelle valeur, 13,2 comprise — la virgule française est acceptée. Deux boutons `A−` / `A+` règlent au dixième de point. Un bouton **Casse** fait tourner la sélection entre MAJUSCULES, minuscules et Première Lettre. |
| **Surligneur** | Sélectionnez, cliquez : c'est surligné. Sans sélection, le surligneur s'arme et l'on passe sur le texte au fil de la lecture, comme avec un vrai marqueur. La couleur **sort au PDF dans tous les cas**, y compris lorsque « Graphiques d'arrière-plan » reste décoché dans la fenêtre d'impression. |
| **Encadrés** | Définition, Théorème, Attention, Méthode — plus des zones colorées libres en huit teintes. Deux pressions rapides sur `Entrée` font sortir du cadre. |
| **Images** | Redimensionnement au curseur, recadrage réversible, glisser-déposer, et du texte qui contourne l'image à gauche ou à droite. Les photos sont allégées automatiquement à l'insertion. |
| **Icônes** | 191 pictogrammes classés en 8 familles, insérables à quatre tailles : pédagogie, maths (triangle rectangle, fractions, suites, ∑, Δ, π, ⊥, ∥, x̄, σ…), intelligence artificielle, chapitres, filières du lycée, fournitures, symboles, évaluation. |
| **Atelier de ressources** | Un bouton fabrique le prompt à coller dans une conversation avec une intelligence artificielle, un autre importe sa réponse : cours, fiche de révision, évaluation par compétences, QCM, exercices corrigés. Le modèle n'écrit jamais de HTML — il remplit un vocabulaire fermé, l'application dessine. Quatre raccourcis ouvrent ChatGPT, Gemini, Claude ou l'Assistant IA souverain de l'Éducation nationale. |
| **Programme embarqué** | Six niveaux — 3ᵉ Prépa-Métiers, CAP, 2ᵈᵉ, 1ʳᵉ, Terminale, UPE2A — 28 thèmes, 86 chapitres, 507 items, chacun avec sa référence de Bulletin officiel. Arbre pliable, barre de recherche, sélection d'un chapitre entier ou item par item, à travers plusieurs niveaux. Saisie libre pour le reste. |
| **Différenciation** | Un seul fichier porte le parcours standard, « Pour aller plus loin » et « Je revois pas à pas ». Les trois partagent le même tronc commun et ne peuvent pas diverger ; la copie de l'élève ne dit jamais laquelle il a reçue. |
| **Contrôle qualité** | À l'import, l'application refait tous les calculs des corrections, refuse un nombre sans origine, une capacité hors programme, un QCM sans bonne réponse, un exercice sans correction. |
| **Compétences** | Les cinq compétences du Bac Pro — S'approprier, Raisonner, Réaliser, Valider, Communiquer — en pastilles colorées, pastille seule ou avec son nom. Elles s'insèrent, se copient et s'effacent comme des caractères, et gardent leur couleur à l'impression. |

#### Tout reste à vous, même ce qui vient de l'intelligence artificielle

Un bloc généré n'a aucun statut à part : c'est le même objet qu'un bloc posé à la main.

| | |
|---|---|
| **Déplacer** | Au survol d'un bloc — formule, zone colorée, exercice, QCM, tableau — une poignée apparaît. `⠿` le fait glisser ailleurs dans le document, un repère montrant où il tombera. |
| **Respirer autour** | `↑＋` et `↓＋` insèrent un paragraphe juste avant ou juste après le bloc. Un bloc en tête de document, en queue, ou collé à un autre, laisse toujours une place où écrire : plus de bloc impossible à dépasser au clavier. |
| **Dupliquer, supprimer** | `⧉` recopie le bloc, `🗑` l'efface — comme n'importe quel caractère. |
| **Redimensionner** | Deux prises, en bord droit et en bord bas, règlent la largeur et la hauteur à la souris. |
| **Restyler** | La taille de police, la casse et le surlignage s'appliquent **à l'intérieur** d'un exercice ou d'un QCM, même quand la sélection n'en prend qu'une partie. |

### ∫ Formules

| | |
|---|---|
| **Commandes `/`** | 90 formules prêtes : `/pythagore`, `/discriminant`, `/tva`, `/marge`, `/seuil-rentabilite`, `/mensualite`… plus `/qcm` et `/exercice` pour créer un bloc sans quitter le clavier. |
| **Symboles `//`** | 46 symboles isolés : `//alpha` → α, `//x_bar` → x̄, `//infty` → ∞. Les accents dynamiques (`//v_vec`, `//t_hat`) sont générés à la volée. |
| **Saisie éclair** | `Ctrl + /` écrit une formule au fil du texte, à la manière d'une calculatrice : `*` devient ×, `a/b` devient une fraction. |
| **Édition directe** | 1 clic sélectionne la formule · 2 clics modifient la lettre ou le nombre cliqué · 3 clics ouvrent l'éditeur complet. |

### ⊞ Tableaux et tableur

| | |
|---|---|
| **Tableaux** | Largeur au choix — 100 %, 75 %, 50 % ou ajustée au contenu — et placement à gauche, centré ou à droite : un tableau ne prend plus toute la page malgré vous. Colonnes ajustables à la souris, retour à la ligne automatique dans les cellules. **⬚ Tout sélectionner** saisit toutes les cases d'un coup, pour tout centrer ou tout mettre en gras en une fois. |
| **Tableur** | 35 fonctions de calcul en français (`SOMME`, `MOYENNE`, `SI`, `RECHERCHEV`…), recopie d'une formule par glissement, et rendu identique à l'export. |

### 📄 Mise en page

Pagination A4 automatique, saut de page manuel, numérotation optionnelle, duplication et
déplacement de page, et un aperçu qui correspond exactement au PDF produit. Un bloc qui ne tient
pas en bas de page passe entier sur la suivante ; un paragraphe plus long qu'une page, lui, se
poursuit page suivante, la coupure tombant entre deux mots. Seules une page vierge insérée ou
une page dupliquée gardent des limites fixes : partout ailleurs, effacer quelques mots fait
remonter le texte de lui-même.

### 🔍 Zoom

La feuille grossit de 50 % à 300 % : boutons en bas à droite de l'écran, `Ctrl +` / `Ctrl −` /
`Ctrl 0`, ou `Ctrl` + molette. Sur Mac, `Cmd` fait le même office.

**Le zoom ne porte que sur la feuille.** Ruban, rail, panneau latéral et barre de zoom gardent
leur taille : agrandir le texte ne repousse jamais un bouton hors de l'écran. Le niveau est
mémorisé d'une session à l'autre, et **l'impression sort toujours à 100 %** — zoomer ne change
rien au PDF.

### 📱 Écrans étroits et tablettes

En dessous de 1100 px, le ruban et la barre de symboles **se replient sur plusieurs rangées**
au lieu de défiler : toutes les icônes restent atteignables au doigt, sans faire glisser la
barre horizontalement. Le panneau de droite se superpose à la page au lieu de la rétrécir, et
la feuille est ajustée à la largeur disponible en gardant ses proportions A4 exactes.

---

## Raccourcis

| Raccourci | Effet |
|---|---|
| `Ctrl` + `B` / `I` / `U` | Gras · italique · souligné |
| `Ctrl` + `Z` / `Y` | Annuler · rétablir |
| `Ctrl` + `F` | Rechercher dans le document |
| `Ctrl` + `K` | Insérer un lien |
| `Ctrl` + `S` | Enregistrer le projet |
| `Ctrl` + `P` | Imprimer ou exporter en PDF |
| `Ctrl` + `/` | Saisie éclair d'une formule |
| `/` + un mot | Formule prête (`/tva`, `/pythagore`, `/marge`) |
| `//` + un mot | Symbole isolé (`//alpha`, `//x_bar`) |
| `/qcm` · `/exercice` | Créer un QCM ou un exercice |
| `Entrée` `Entrée` (< 0,3 s) | Sortir d'un encadré |
| `Entrée` dans un QCM | Passer à la réponse suivante (`Maj`+`Entrée` : revenir à la ligne) |

---

## Bibliothèque de modèles

**13 chapitres · 97 modèles · 194 exemples.**

| Chapitre | Contenu |
|---|---|
| Calcul numérique | Identités remarquables, puissances, racines, notation scientifique, fractions, arrondis, conversions |
| Proportionnalité & % | Quatrième proportionnelle, règle de trois, taux d'évolution, évolutions successives, partage proportionnel |
| **💶 Calculs commerciaux** | Coût d'achat, prix de revient, marge, taux de marge et de marque, coefficient multiplicateur, TVA, remise, escompte, facture, chiffre d'affaires |
| **🏷️ Prix & rentabilité** | Charges fixes et variables, marge sur coût variable, seuil de rentabilité, point mort, marge de sécurité, prix psychologique, pouvoir d'achat |
| **🏦 Finance & paie** | Intérêts simples et composés, valeur acquise, mensualité de crédit, taux d'endettement, amortissement, brut → net, coût employeur |
| Fonctions | Affine, linéaire, degré 2, inverse, lecture graphique, coût-recette-bénéfice, logarithme, exponentielle |
| Équations | 1er degré, inéquations, discriminant, droite par deux points, systèmes, tableaux de signes |
| Suites | Arithmétiques, géométriques, sommes, sens de variation |
| Géométrie plane | Pythagore, Thalès, trigonométrie, aires, périmètres, échelles, distances |
| Géométrie 3D | Volumes, aires des solides, agrandissement-réduction, capacités |
| Statistiques | Moyenne pondérée, variance, médiane et quartiles, fréquences, étendue, effectifs cumulés |
| Probabilités | Événement, contraire, réunion, conditionnelle, probabilités totales, loi binomiale |
| Analyse | Dérivée, dérivées usuelles, variations, primitives, intégrale, valeur moyenne |

### Les deux boutons d'exemple

Chaque modèle propose, à côté de « En bloc » et « En ligne » :

- **💡 Exemple** — la formule appliquée à des nombres, menée jusqu'au résultat.
- **🏭 Situation pro** — une courte scène de métier (négoce, atelier, chantier, restauration,
  paie, dossier de prêt) avec les données, le calcul et la réponse rédigée.

Les deux s'insèrent dans une zone colorée **entièrement modifiable** : chiffres, noms, contexte.
Placés à l'intérieur d'un encadré existant, ils s'insèrent sans créer de zone, pour ne jamais
imbriquer deux cadres.

> **Chaque exemple se comprend seul.** Toutes ses données sont énoncées et chaque résultat est
> calculé : aucun chiffre n'est emprunté à un autre modèle. Un contrôle automatique refuse tout
> exemple contenant une valeur qui ne serait ni donnée dans l'énoncé, ni obtenue par un calcul
> affiché — et tous les résultats chiffrés sont recalculés avant publication.

---

## Évaluer : exercices et QCM

### 📝 Exercices

Un bloc par exercice, numéroté automatiquement et renommable d'un clic. **Valider** verrouille
l'énoncé et fait apparaître la correction, repliable.

### ☑️ QCM

- Nombre de questions et de réponses choisis à la création, **ajustables ensuite question par
  question** (`＋` / `－` / `✕`).
- Bascule **☐ / ◯** par question : plusieurs bonnes réponses, ou une seule.
- La bonne réponse se désigne **d'un clic sur sa case**.
- **✎ Correction par question** : chaque question a son propre commentaire, qui la suit partout.
  Un commentaire général du QCM reste disponible sous le bloc.
- Bouton **🎓 / 🙈** : masque ou réaffiche les bonnes réponses dans l'éditeur — la vue masquée
  est exactement celle des élèves.
- **🗑 Corbeille** pour supprimer le QCM entier, avec confirmation et annulation par `Ctrl+Z`.
- **Plus long qu'une page ?** Le QCM se poursuit sur la page suivante, en coupant *entre* deux
  questions : une question n'est jamais séparée de ses réponses ni de son commentaire.

---

## Distribuer : PDF et page web

| Sortie | Ce qu'elle produit |
|---|---|
| **🖨 Version élève** | PDF sans les corrections d'exercices, QCM aux cases vides. |
| **🖨 Version professeur** | PDF avec les corrections dépliées et les bonnes réponses cochées. |
| **🌐 Page Web** | Un fichier HTML **autonome**, à déposer sur un ENT ou à envoyer : les formules s'affichent même sans connexion. Les corrections restent repliées, et **le QCM devient interactif** — l'élève coche, clique sur *Vérifier mes réponses*, obtient son score, et les bonnes réponses apparaissent en orange. |
| **💾 Projet** | Un fichier réouvrable dans MathNotes, pour reprendre le cours plus tard ou sur un autre poste. |

> ⚠️ Dans la page web exportée, les réponses attendues sont encodées mais restent techniquement
> retrouvables dans le code source. Pour un devoir noté, préférez le PDF version élève.

---

## Vos cours et leur sécurité

| | |
|---|---|
| **📚 Mes cours** | Plusieurs documents conservés dans le navigateur, avec leur date et leur poids. Renommer, ouvrir, dupliquer, supprimer. Une jauge indique l'espace occupé ; le dernier cours ne peut pas être supprimé. |
| **Sauvegarde surveillée** | L'enregistrement automatique ne peut plus échouer en silence : un bandeau rouge prévient aussitôt, explique la cause (espace saturé, navigation privée) et propose d'enregistrer le fichier. |
| **↩ Restaurer** | Après une feuille blanche, la version effacée reste récupérable en un clic — y compris après avoir fermé et rouvert l'application. |
| **Images allégées** | Une photo est ramenée à 1600 px et recompressée à l'insertion : cinq à dix fois plus légère, sans perte visible à l'impression. La transparence d'un PNG est préservée, et le gain obtenu vous est annoncé. |
| **Verrou entre onglets** | Si le même cours est déjà ouvert ailleurs, le second onglet passe en lecture seule plutôt que d'écraser votre travail. « Reprendre la main » récupère d'abord ce que l'autre onglet a écrit. |

---

## Confidentialité

Tout s'exécute dans le navigateur. **Aucun compte, aucun serveur, aucune publicité, aucun suivi.**
Les cours sont enregistrés localement sur le poste, et récupérables à tout moment sous forme de
fichier projet, de PDF ou de page web. Rien n'est transmis à un tiers.

---

## Sous le capot

- **Un seul fichier HTML** (1,30 Mo, ~520 Ko une fois compressé par le serveur) : structure,
  styles, code, moteur mathématique et polices réunis. Rien à compiler, rien à installer,
  aucun cadriciel.
- **Rendu des formules** : [KaTeX](https://katex.org/) 0.16.9 **embarqué**, avec ses 20 polices
  en données intégrées. Aucun appel réseau n'est fait pour écrire ou afficher des mathématiques.
- **Typographie de l'interface** : DM Sans, DM Mono et Lora via Google Fonts, avec repli
  automatique sur les polices du système si elles ne se chargent pas.
- **Pagination A4** calculée en JavaScript, avec des espaceurs invisibles pour qu'aucune ligne
  ne se retrouve dans le blanc entre deux pages : un bloc indivisible passe entier page suivante,
  un QCM se coupe entre deux questions, un paragraphe se coupe entre deux mots. Les mêmes
  espaceurs deviennent des coupures de page forcées à l'impression, ce qui garantit le même
  nombre de pages à l'écran et sur le papier.
- **Impression** : feuille de style construite en liste blanche, pour que seule la page du cours
  soit imprimée et que la page 1 de l'écran soit la page 1 du PDF. Les teintes de l'impression
  sont celles de l'écran ; chaque encadré porte en plus un contour de sa couleur, qui s'imprime
  même quand l'option « Graphiques d'arrière-plan » du navigateur reste décochée.
- **Export web** : les styles sont dérivés de la feuille de style de l'éditeur lui-même, de sorte
  que l'écran et l'export ne peuvent pas diverger.
- **Zoom** : la mise à l'échelle vit sur un seul conteneur, autour de la feuille. Le facteur est
  **lu dans la matrice de transformation**, jamais estimé : tout calcul de mise en page reste
  juste à n'importe quel niveau de zoom, et l'impression sort toujours à 100 %.
- **Compatibilité** : aucune syntaxe récente (`?.`, `??`, `:has()`, `structuredClone`) — les
  versions anciennes de Safari et Firefox sont prises en charge. Windows et macOS, clavier
  `Ctrl` ou `Cmd` selon la machine.

---

## Développement et tests

Le projet n'a pas de chaîne de compilation : `MathNotes.html` s'édite directement. Les outils
ci-dessous servent à garantir qu'une modification n'en casse pas une autre. **718 vérifications
réparties en 22 suites, plus trois audits.**

| Script | Rôle |
|---|---|
| `catalog_test.py` | Rend les 278 formules et 194 exemples du catalogue et échoue si l'un d'eux ne s'affiche pas |
| `exc_audit.py` | Refuse tout exemple contenant un nombre qui n'est ni donné ni calculé |
| `qcm_test.py` · `qcm2_test.py` | Cycle complet du QCM : création, édition, correction par question, corbeille, impression, export interactif |
| `ex_test.py` | Insertion des exemples et absence d'imbrication de zones |
| `regress_test.py` | Non-régression : ruban, formules, tableaux, tableur, exercices, pagination, réouverture |
| `pdf_test.py` · `qcm_pdf_test.py` | Correspondance page écran ↔ page PDF, versions élève et professeur, coupure du QCM entre questions |
| `print_audit.py` | Compare l'écran et l'impression élément par élément : aucune différence de fond, aucun outil d'édition sur le papier |
| `lib_test.py` | Bibliothèque de cours et alerte de sauvegarde |
| `img2_test.py` | Réduction des images, transparence, non-régression de l'insertion |
| `safety_test.py` | Filet de sécurité de la feuille blanche et verrou entre onglets |
| `offline_test.py` | Application et exports vérifiés **réseau totalement coupé** |
| `tablet_test.py` | Écrans étroits, sans rien changer au-dessus de 1100 px |
| `idb_test.py` · `leak_test.py` · `fmt_test.py` | Stockage large : capacité, reprise vérifiée, aucune écriture qui s'accumule, jauge lisible |
| `comp_test.py` | Pastilles de compétences : insertion, effacement, taille, couleurs, impression, export |
| `pg_test.py` | Coupure des longs paragraphes, aucune ligne dans le blanc, outils de page qui ne figent rien |
| `mnr_test.py` | Atelier : chaque bloc produit son objet, les trois parcours sortent d'une source, chaque classe de défaut est arrêtée |
| `demo_atelier.py` | La boucle complète sur une ressource réelle : programme → prompt → ressource → contrôle → trois parcours → PDF |
| `porte_test.py` | Une seule porte d'entrée : projet, ressource et programme reconnus à leur forme, l'emballage des assistants retiré, le HTML d'un projet jamais abîmé |
| `zoom_test.py` | Zoom de la feuille : mise en page identique à tout niveau, seule la feuille grossit, clavier PC et Mac, molette, mémorisation, impression toujours à 100 % |
| `edit_test.py` | Surlignage direct et imprimé, respiration autour des blocs, poignée et déplacement, redimensionnement, taille de police libre, casse, largeur et alignement des tableaux, icônes |
| `cours_test.py` | Le cours de démonstration réimporté dans l'application, de bout en bout |
| `check_calls.py` | Détecte les appels à des fonctions inexistantes |
| `build_guide.py` · `guide_pdf.py` | Régénèrent le guide à partir de l'onglet Tuto de l'application |

```bash
npm install                 # KaTeX et polices, pour la compilation du fichier et les tests
pip install playwright beautifulsoup4
python3 catalog_test.py && python3 regress_test.py && python3 qcm_test.py \
  && python3 offline_test.py && python3 pdf_test.py && python3 edit_test.py
```

La batterie complète, telle qu'elle est passée avant chaque livraison :

```bash
for t in catalog_test exc_audit ex_test qcm_test qcm2_test regress_test \
         pdf_test qcm_pdf_test lib_test img2_test safety_test offline_test \
         tablet_test idb_test leak_test fmt_test comp_test pg_test mnr_test \
         demo_atelier porte_test zoom_test edit_test cours_test print_audit; do
  printf '%-16s ' $t; python3 $t.py 2>&1 | tail -1
done
```

Le guide et la présentation sont **générés à partir de l'application elle-même** : ils ne peuvent
pas se désynchroniser du produit.

---

## Feuille de route

- [ ] Barème et note chiffrée sur les QCM
- [ ] Génération d'une version B d'un QCM (ordre des réponses mélangé)
- [ ] Banque de situations professionnelles par filière
- [ ] Insertion de graphiques de fonctions
- [ ] Étiquettes d'accessibilité sur les boutons à icône

---

## Auteur

**Tom Rougeaud** — professeur de mathématiques en lycée professionnel.

- [LinkedIn](https://www.linkedin.com/in/tomrougeaud/)
- [Mon Casier Pédagogique Numérique](https://tom-rougeaud.github.io/casier/)

---

## Licence

Le code de MathNotes est à placer sous la licence de votre choix : la licence **MIT**
(réutilisation libre avec mention de l'auteur) ou **CC BY-NC-SA 4.0** (partage non commercial,
dans les mêmes conditions) conviennent bien à un usage pédagogique partagé. Ajoutez le fichier
`LICENSE` correspondant à la racine du dépôt.

MathNotes intègre [KaTeX](https://katex.org/) (licence MIT, © Khan Academy et contributeurs) ;
le texte de cette licence doit être conservé avec le projet.
