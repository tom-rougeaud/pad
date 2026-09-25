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
   réel. Mêmes couleurs, même pagination, et jamais un tableau, une formule, un exercice ou une
   question de QCM coupés entre deux pages.
2. **Le contenu est déjà là.** 97 modèles de formules, chacun accompagné d'une application
   chiffrée et d'une situation professionnelle, prêts à insérer et entièrement modifiables.
3. **Rien ne dépend du réseau.** Le moteur mathématique et ses polices sont contenus dans le
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
| **Encadrés** | Définition, Théorème, Attention, Méthode — plus des zones colorées libres en huit teintes. Deux pressions rapides sur `Entrée` font sortir du cadre. |
| **Images** | Redimensionnement au curseur, recadrage réversible, glisser-déposer, et du texte qui contourne l'image à gauche ou à droite. Les photos sont allégées automatiquement à l'insertion. |
| **Icônes** | 150 pictogrammes classés en 7 familles (pédagogie, maths, filières, évaluation…), insérables à quatre tailles. |

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
| **Tableaux** | Largeurs de colonnes ajustables à la souris, jamais plus larges que la page, retour à la ligne automatique dans les cellules. |
| **Tableur** | 35 fonctions de calcul en français (`SOMME`, `MOYENNE`, `SI`, `RECHERCHEV`…), recopie d'une formule par glissement, et rendu identique à l'export. |

### 📄 Mise en page

Pagination A4 automatique, saut de page manuel, numérotation optionnelle, duplication et
déplacement de page, et un aperçu qui correspond exactement au PDF produit.

### 📱 Écrans étroits

En dessous de 1100 px, le ruban et la barre de symboles passent sur une rangée défilable au
doigt, et le panneau de droite se superpose à la page au lieu de la rétrécir. La feuille garde
ses proportions A4 exactes : elle défile horizontalement plutôt que de se déformer.

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

- **Un seul fichier HTML** (1,10 Mo, ~470 Ko une fois compressé par le serveur) : structure,
  styles, code, moteur mathématique et polices réunis. Rien à compiler, rien à installer,
  aucun cadriciel.
- **Rendu des formules** : [KaTeX](https://katex.org/) 0.16.9 **embarqué**, avec ses 20 polices
  en données intégrées. Aucun appel réseau n'est fait pour écrire ou afficher des mathématiques.
- **Typographie de l'interface** : DM Sans, DM Mono et Lora via Google Fonts, avec repli
  automatique sur les polices du système si elles ne se chargent pas.
- **Pagination A4** calculée en JavaScript, avec des espaceurs invisibles pour qu'aucun bloc ne
  chevauche une coupure de page — y compris à l'intérieur d'un QCM, qui se coupe entre deux
  questions.
- **Impression** : feuille de style construite en liste blanche, pour que seule la page du cours
  soit imprimée et que la page 1 de l'écran soit la page 1 du PDF. Les teintes de l'impression
  sont celles de l'écran ; chaque encadré porte en plus un contour de sa couleur, qui s'imprime
  même quand l'option « Graphiques d'arrière-plan » du navigateur reste décochée.
- **Export web** : les styles sont dérivés de la feuille de style de l'éditeur lui-même, de sorte
  que l'écran et l'export ne peuvent pas diverger.
- **Compatibilité** : aucune syntaxe récente (`?.`, `??`, `:has()`, `structuredClone`) — les
  versions anciennes de Safari et Firefox sont prises en charge.

---

## Développement et tests

Le projet n'a pas de chaîne de compilation : `MathNotes.html` s'édite directement. Les outils
ci-dessous servent à garantir qu'une modification n'en casse pas une autre. **248 vérifications
réparties en 13 suites, plus deux audits.**

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
| `check_calls.py` | Détecte les appels à des fonctions inexistantes |
| `build_guide.py` · `guide_pdf.py` | Régénèrent le guide à partir de l'onglet Tuto de l'application |

```bash
npm install                 # KaTeX et polices, pour la compilation du fichier et les tests
pip install playwright beautifulsoup4
python3 catalog_test.py && python3 regress_test.py && python3 qcm_test.py \
  && python3 offline_test.py && python3 pdf_test.py
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
