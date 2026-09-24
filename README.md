<div align="center">

# Σ MathNotes

**Écrire, illustrer et évaluer un cours de mathématiques de lycée professionnel — dans un seul fichier.**

Un éditeur de cours qui met les formules à portée de clavier, propose 97 modèles prêts à l'emploi
avec leurs exemples, génère des QCM corrigés, et produit un PDF conforme au pixel près à ce que
vous voyez à l'écran.

[![Fichier unique](https://img.shields.io/badge/fichier-unique-27AE60)](#)
[![Sans installation](https://img.shields.io/badge/installation-aucune-2F80ED)](#)
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

MathNotes réunit les trois, avec deux partis pris :

1. **Ce que vous voyez est ce qui s'imprime.** La page à l'écran est une A4 paginée en temps
   réel. Jamais un tableau, une formule, un exercice ou un QCM coupé entre deux pages.
2. **Le contenu est déjà là.** 97 modèles de formules, chacun accompagné d'une application
   chiffrée et d'une situation professionnelle, prêts à insérer et entièrement modifiables.

---

## Démarrage

**En ligne** — ouvrez la page publiée du dépôt (GitHub Pages).

**En local** — téléchargez `MathNotes.html` et ouvrez-le dans votre navigateur. Il n'y a rien à
installer, ni compte à créer.

Premiers gestes, dans l'ordre :

```
1. Écrivez trois lignes de cours.
2. Tapez  /tva   → la formule s'écrit toute seule.
3. Panneau de droite → onglet Modèles → 🏭 Situation pro.
4. Ruban → ☑️ QCM → cochez la bonne réponse.
5. Ruban → 🖨 Imprimer → Version élève ou Version professeur.
```

L'onglet **🎓 TUTO** de l'application contient 23 fiches et 42 questions fréquentes.
Un guide complet est également disponible en PDF.

---

## Fonctionnalités

### ✍️ Rédaction

| | |
|---|---|
| **Ruban complet** | Gras, italique, souligné, titres, listes, citation, code, surligneur, couleurs, police et taille. Les raccourcis habituels d'un traitement de texte fonctionnent. |
| **Encadrés** | Définition, Théorème, Attention, Méthode — plus des zones colorées libres en huit teintes. Deux pressions rapides sur `Entrée` font sortir du cadre. |
| **Images** | Redimensionnement au curseur, recadrage réversible, glisser-déposer, et du texte qui contourne l'image à gauche ou à droite. |
| **Icônes** | 150 pictogrammes classés en 7 familles (pédagogie, maths, filières, évaluation…), insérables à quatre tailles. |

### ∫ Formules

| | |
|---|---|
| **Commandes `/`** | 100 formules prêtes : `/pythagore`, `/discriminant`, `/tva`, `/marge`, `/seuil-rentabilite`, `/mensualite`… |
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

> Tous les résultats chiffrés du catalogue sont recalculés et vérifiés automatiquement avant
> publication, et chaque formule est rendue par un test de non-régression.

---

## Évaluer : exercices et QCM

### 📝 Exercices

Un bloc par exercice, numéroté automatiquement et renommable d'un clic. **Valider** verrouille
l'énoncé et fait apparaître la correction, repliable.

### ☑️ QCM

- Nombre de questions et de réponses choisis à la création, **ajustables ensuite question par
  question** (`＋` / `－` / `✕`).
- Bascule **☐ / ◯** par question : plusieurs bonnes réponses, ou une seule.
- La bonne réponse se désigne **d'un clic sur sa case**. Un commentaire de correction rédigé
  peut s'ajouter, sans obligation.
- Bouton **🎓 / 🙈** : masque ou réaffiche les bonnes réponses dans l'éditeur — la vue masquée
  est exactement celle des élèves.
- Retour à la ligne automatique dans les cellules, et un QCM n'est jamais coupé entre deux pages.

---

## Distribuer : PDF et page web

| Sortie | Ce qu'elle produit |
|---|---|
| **🖨 Version élève** | PDF sans les corrections d'exercices, QCM aux cases vides. |
| **🖨 Version professeur** | PDF avec les corrections dépliées et les bonnes réponses cochées. |
| **🌐 Page Web** | Un fichier HTML autonome, à déposer sur un ENT ou à envoyer. Les corrections d'exercices restent repliées derrière un bouton, et **le QCM devient interactif** : l'élève coche, clique sur *Vérifier mes réponses*, et obtient son score — le juste en vert, le faux en rouge, les oublis entourés. |
| **💾 Projet** | Un fichier réouvrable dans MathNotes, pour reprendre le cours plus tard ou sur un autre poste. |

> ⚠️ Dans la page web exportée, les réponses attendues sont encodées mais restent techniquement
> retrouvables dans le code source. Pour un devoir noté, préférez le PDF version élève.

---

## Confidentialité

Tout s'exécute dans le navigateur. **Aucun compte, aucun serveur, aucune publicité, aucun suivi.**
Les cours sont enregistrés localement sur le poste, et récupérables à tout moment sous forme de
fichier projet, de PDF ou de page web. Rien n'est transmis à un tiers.

---

## Sous le capot

- **Un seul fichier HTML** (~460 Ko) : structure, styles et code réunis. Rien à compiler,
  rien à installer, aucun cadriciel.
- **Rendu des formules** : [KaTeX](https://katex.org/) 0.16.9, chargé depuis un CDN.
- **Typographie** : DM Sans, DM Mono et Lora, via Google Fonts.
- **Pagination A4** calculée en JavaScript, avec des espaceurs invisibles pour qu'aucun bloc ne
  chevauche une coupure de page.
- **Impression** : feuille de style construite en liste blanche, pour que seule la page du cours
  soit imprimée et que la page 1 de l'écran soit la page 1 du PDF.
- **Export web** : les styles sont dérivés de la feuille de style de l'éditeur lui-même, de sorte
  que l'écran et l'export ne peuvent pas diverger.

> Les formules et les polices sont chargées depuis Internet : prévoyez une connexion lors de la
> première ouverture.

---

## Développement et tests

Le projet n'a pas de chaîne de compilation : `MathNotes.html` s'édite directement. Les outils
ci-dessous servent à garantir qu'une modification n'en casse pas une autre.

| Script | Rôle |
|---|---|
| `catalog_test.py` | Rend les 278 formules et 194 exemples du catalogue et échoue si l'un d'eux ne s'affiche pas |
| `qcm_test.py` | Cycle complet du QCM : création, édition, correction, impression, export interactif |
| `ex_test.py` | Insertion des exemples et absence d'imbrication de zones |
| `regress_test.py` | Non-régression : ruban, formules, tableaux, tableur, exercices, pagination, réouverture |
| `pdf_test.py` | Correspondance page écran ↔ page PDF, absence d'éléments de menu, versions élève et professeur |
| `check_calls.py` | Détecte les appels à des fonctions inexistantes |
| `build_guide.py` · `guide_pdf.py` | Régénèrent le guide à partir de l'onglet Tuto de l'application |

```bash
npm install                 # KaTeX et polices, pour les tests hors ligne
pip install playwright beautifulsoup4
python3 catalog_test.py && python3 regress_test.py && python3 qcm_test.py && python3 pdf_test.py
```

Le guide et sa version PDF sont **générés à partir du Tuto de l'application** : ils ne peuvent
donc pas se désynchroniser du produit.

---

## Feuille de route

- [ ] Barème et note chiffrée sur les QCM
- [ ] Génération d'une version B d'un QCM (ordre des réponses mélangé)
- [ ] Banque de situations professionnelles par filière
- [ ] Insertion de graphiques de fonctions

---

## Auteur

**Tom Rougeaud** — professeur de mathématiques en lycée professionnel.

- [LinkedIn](https://www.linkedin.com/in/tomrougeaud/)
- [Mon Casier Pédagogique Numérique](https://tom-rougeaud.github.io/casier/)

---

## Licence

À définir. Pour un usage pédagogique partagé, la licence **MIT** (réutilisation libre, avec
mention de l'auteur) ou **CC BY-NC-SA 4.0** (partage non commercial, dans les mêmes conditions)
conviennent bien ; ajoutez le fichier `LICENSE` correspondant à la racine du dépôt.
