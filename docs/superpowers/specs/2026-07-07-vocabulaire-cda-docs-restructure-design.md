# Restructuration de la documentation vocabulaire CDA

## Contexte

Le `README.md` du dépôt `memoVocab-cda` contient actuellement 4 sections de vocabulaire (Git/GitHub, SQL/PostgreSQL, JavaScript, CSS/Thèmes) sous forme de tableaux markdown, toutes dans un seul fichier de 224 lignes. L'objectif est de scinder ce contenu en plusieurs fichiers thématiques, d'ajouter une navigation façon documentation (table des matières, structure du projet, badges de pagination), en s'inspirant du style de deux dépôts existants de l'utilisatrice :

- [`carte-de-visite.fannysaez`](https://github.com/fannysaez/carte-de-visite.fannysaez) : badges technos shields.io avec logos, table des matières numérotée.
- [`doc-sql`](https://github.com/fannysaez/doc-sql) : documentation éclatée en plusieurs fichiers `.md`, arborescence de dossier affichée dans le README, navigation "Suivant" en bas de page.

## Décisions validées avec l'utilisatrice

- Nom du dossier de documentation : `vocabulaire-cda/`
- Pas de dossier `assets/` pour l'instant (le contenu actuel est uniquement du texte/tableaux)
- Badges de pagination au format shields.io (coloré), pas de simples liens texte
- Découpage en 4 fichiers, un par section actuelle du README

## Structure cible

```
memoVocab-cda/
├── README.md
└── vocabulaire-cda/
    ├── git-github.md
    ├── sql-postgresql.md
    ├── javascript.md
    └── css-themes.md
```

Chaque fichier reprend telle quelle la section correspondante du `README.md` actuel (tableaux et blocs de code CSS inclus) — aucun contenu de vocabulaire n'est réécrit ou perdu, uniquement déplacé.

Correspondance section → fichier :

| Section actuelle du README | Nouveau fichier |
| --- | --- |
| 🔧 GIT / GITHUB | `vocabulaire-cda/git-github.md` |
| 🗄️ SQL / POSTGRESQL | `vocabulaire-cda/sql-postgresql.md` |
| 🟨 JAVASCRIPT | `vocabulaire-cda/javascript.md` |
| 🎨 CSS / THÈMES | `vocabulaire-cda/css-themes.md` |

Ordre de navigation (pagination) : `README.md` → `git-github.md` → `sql-postgresql.md` → `javascript.md` → `css-themes.md`.

## README.md (nouveau contenu)

1. Titre `# Mémo Vocabulaire CDA` + une phrase de description courte.
2. Une ligne de badges technos shields.io avec logos (style `carte-de-visite`), un badge par thème couvert : Git, PostgreSQL, JavaScript, CSS3. Badges statiques (pas de lien externe), purement décoratifs pour indiquer les technos couvertes.
3. Section `## 📑 Table des matières` : liste numérotée de 4 liens vers les fichiers de `vocabulaire-cda/`.
4. Section `## 📂 Structure du projet` : arborescence en bloc de code (```), reprenant la structure cible ci-dessus.
5. En bas de fichier : un badge de pagination `Suivant ▶` pointant vers `vocabulaire-cda/git-github.md` (pas de badge "Précédent" sur le README, puisque c'est la racine).

## Fichiers de section (`vocabulaire-cda/*.md`)

Chaque fichier suit ce gabarit :

1. Titre de section avec l'emoji existant (ex : `# 🔧 Git / GitHub`).
2. Contenu déplacé tel quel depuis le README actuel (tableaux, sous-titres `###`, blocs de code).
3. En bas de fichier, une ligne de badges de navigation :
   - `◀ Précédent` — absent sur le premier fichier (`git-github.md`), qui n'a que Sommaire + Suivant.
   - `🏠 Sommaire` — présent sur tous les fichiers, pointe vers `../README.md`.
   - `Suivant ▶` — absent sur le dernier fichier (`css-themes.md`).

## Format des badges (shields.io)

Badges technos (README, en-tête) — badges "logo" classiques simples-icons, non cliquables :

```
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
```

Badges de pagination (bas de chaque fichier et du README), cliquables (image dans un lien markdown) :

```
[![◀ Précédent](https://img.shields.io/badge/◀-Pr%C3%A9c%C3%A9dent-2E86AB?style=flat-square)](chemin-precedent.md)
[![🏠 Sommaire](https://img.shields.io/badge/🏠-Sommaire-555555?style=flat-square)](../README.md)
[![Suivant ▶](https://img.shields.io/badge/Suivant-%E2%96%B6-2E86AB?style=flat-square)](chemin-suivant.md)
```

## Hors périmètre

- Pas de réécriture ou d'enrichissement du contenu de vocabulaire lui-même (uniquement déplacement).
- Pas de dossier `assets/` (reporté à plus tard si besoin d'images/schémas).
- Pas de changement du contenu technique (CSS, SQL, JS, Git) au-delà du déplacement.
