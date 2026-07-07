# Restructuration Documentation Vocabulaire CDA Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Scinder le `README.md` (224 lignes, 4 sections de vocabulaire) en 4 fichiers thématiques dans `vocabulaire-cda/`, et transformer le `README.md` en page d'accueil avec badges technos, table des matières et structure du projet, avec navigation par badges de pagination entre les fichiers.

**Architecture:** Déplacement de contenu markdown pur, aucune génération de code ni build. Chaque fichier de section est une copie verbatim de la section correspondante du README actuel (titre passé de `##` à `#`), à laquelle on ajoute une ligne de badges de navigation en bas de page. Le README devient un point d'entrée léger.

**Tech Stack:** Markdown, badges shields.io (`img.shields.io/badge/...`).

## Global Constraints

- Dossier de documentation : `vocabulaire-cda/` (validé avec l'utilisatrice)
- Pas de dossier `assets/` dans ce chantier
- Badges de pagination au format shields.io coloré (pas de liens texte simples)
- Contenu de vocabulaire déplacé **verbatim** — aucune reformulation, aucun ajout/suppression de lignes de tableau
- Ordre de navigation fixe : `README.md` → `git-github.md` → `sql-postgresql.md` → `javascript.md` → `css-themes.md`
- Une fois la migration vérifiée, le dossier `docs/` (specs + plans) est supprimé du dépôt (demande explicite de l'utilisatrice — ce ne sont que des artefacts de travail, pas un livrable)

---

### Task 1: Créer `vocabulaire-cda/git-github.md`

**Files:**
- Create: `vocabulaire-cda/git-github.md`
- Modify (later, Task 5): `README.md` (suppression de cette section)

**Interfaces:**
- Produces: fichier `vocabulaire-cda/git-github.md`, premier maillon de la chaîne de pagination (pas de badge "◀ Précédent", lien "Suivant ▶" vers `sql-postgresql.md`)

- [ ] **Step 1: Créer le fichier avec le contenu déplacé + badges de navigation**

Créer `vocabulaire-cda/git-github.md` avec exactement ce contenu :

```markdown
# 🔧 GIT / GITHUB

| Commande | Définition | À quoi ça sert |
| --- | --- | --- |
| `git init` | Initialise un dépôt Git | Démarrer le suivi de version dans un dossier |
| `git clone <url>` | Copie un dépôt distant en local | Récupérer un projet existant |
| `git status` | Affiche l'état des fichiers | Voir ce qui a changé / est en attente |
| `git add <fichier>` | Ajoute au "staging area" | Préparer un fichier avant commit |
| `git commit -m "msg"` | Enregistre les changements | Créer un point de sauvegarde versionné |
| `git log` | Historique des commits | Voir qui a fait quoi, quand |
| `git diff` | Différences entre versions | Comparer avant/après modification |
| `git branch` | Liste/crée des branches | Travailler en parallèle sans casser le code principal |
| `git checkout <branche>` | Change de branche | Se déplacer entre versions du code |
| `git switch <branche>` | Équivalent moderne de checkout | Changer de branche |
| `git merge <branche>` | Fusionne une branche dans une autre | Intégrer un travail terminé |
| `git rebase` | Réécrit l'historique en réappliquant les commits | Nettoyer l'historique / éviter les merges inutiles |
| `git push` | Envoie les commits locaux vers le distant | Publier son travail |
| `git pull` | Récupère + fusionne les changements distants | Se mettre à jour |
| `git fetch` | Récupère sans fusionner | Voir les changements distants avant de les intégrer |
| `git remote -v` | Liste les dépôts distants liés | Vérifier l'URL du repo (origin) |
| `git stash` | Met de côté des modifs non commitées | Changer de contexte sans perdre son travail |
| `git reset` | Annule des commits (garde ou pas les fichiers) | Revenir en arrière localement |
| `git revert` | Annule un commit en créant un nouveau commit inverse | Annuler proprement sans réécrire l'historique |
| `.gitignore` | Fichier listant ce que Git doit ignorer | Éviter de versionner node_modules, .env, etc. |
| **HEAD** | Pointeur vers le commit courant | Repère "où on en est" |
| **Staging area (index)** | Zone tampon avant le commit | Choisir précisément quoi commiter |
| **Repository (repo)** | Dossier suivi par Git | Le projet versionné |
| **Fork** | Copie d'un repo sur son propre compte GitHub | Contribuer à un projet qu'on ne possède pas |
| **Pull Request (PR)** | Demande de fusion de code sur GitHub | Faire relire/valider avant merge |
| **Merge conflict** | Git ne sait pas choisir entre deux versions | À résoudre manuellement |
| **Clone vs Fork** | Clone = copie locale / Fork = copie sur GitHub | Deux façons de récupérer un projet |

---

[![🏠 Sommaire](https://img.shields.io/badge/🏠-Sommaire-555555?style=flat-square)](../README.md)
[![Suivant ▶](https://img.shields.io/badge/Suivant-%E2%96%B6-2E86AB?style=flat-square)](sql-postgresql.md)
```

- [ ] **Step 2: Vérifier le contenu**

Run: `grep -c "^| \`git" vocabulaire-cda/git-github.md`
Expected: `15` (nombre de lignes de commandes `git ...` dans le tableau)

Run: `grep -q "Suivant" vocabulaire-cda/git-github.md && echo OK`
Expected: `OK`

- [ ] **Step 3: Commit**

```bash
git add vocabulaire-cda/git-github.md
git commit -m "docs: extrait la section Git/GitHub dans vocabulaire-cda/git-github.md"
```

---

### Task 2: Créer `vocabulaire-cda/sql-postgresql.md`

**Files:**
- Create: `vocabulaire-cda/sql-postgresql.md`

**Interfaces:**
- Consumes: `git-github.md` (Task 1) comme cible du badge "◀ Précédent"
- Produces: fichier `vocabulaire-cda/sql-postgresql.md`, badges "◀ Précédent" → `git-github.md`, "Suivant ▶" → `javascript.md`

- [ ] **Step 1: Créer le fichier avec le contenu déplacé + badges de navigation**

Créer `vocabulaire-cda/sql-postgresql.md` avec exactement ce contenu :

```markdown
# 🗄️ SQL / POSTGRESQL (terminal `psql`)

### Commandes terminal `psql`

| Commande | Utilité |
| --- | --- |
| `psql -U user -d dbname` | Se connecter à une base |
| `\l` | Lister les bases de données |
| `\c dbname` | Se connecter à une base |
| `\dt` | Lister les tables |
| `\d nom_table` | Décrire une table (colonnes, types, clés) |
| `\du` | Lister les utilisateurs/rôles |
| `\q` | Quitter psql |

### Langage SQL

| Terme | Définition |
| --- | --- |
| `SELECT` | Sélectionner des données |
| `FROM` | Préciser la table source |
| `WHERE` | Filtrer les lignes |
| `INSERT INTO` | Ajouter une ligne |
| `UPDATE` | Modifier des données existantes |
| `DELETE` | Supprimer des lignes |
| `CREATE TABLE` | Créer une table |
| `ALTER TABLE` | Modifier la structure d'une table |
| `DROP TABLE` | Supprimer une table |

### Clés & contraintes

| Terme | Définition |
| --- | --- |
| **PRIMARY KEY** | Identifiant unique de chaque ligne |
| **FOREIGN KEY** | Clé qui référence la clé primaire d'une autre table (lien entre tables) |
| **UNIQUE** | Impose une valeur non dupliquée |
| **NOT NULL** | Interdit les valeurs vides |
| **DEFAULT** | Valeur automatique si rien n'est fourni |
| **CHECK** | Condition que la valeur doit respecter |
| **SERIAL** | Entier auto-incrémenté (PostgreSQL) |
| **Contrainte** | Règle imposée sur une colonne/table pour garantir l'intégrité des données |

### Relations & jointures

| Terme | Définition |
| --- | --- |
| **INNER JOIN** | Ne garde que les lignes correspondant dans les deux tables |
| **LEFT JOIN** | Garde toutes les lignes de la table de gauche + correspondances |
| **RIGHT JOIN** | Garde toutes les lignes de la table de droite + correspondances |
| **FULL JOIN** | Garde toutes les lignes des deux tables |
| **One-to-many** | Une ligne liée à plusieurs autres (ex: un client → plusieurs commandes) |
| **Many-to-many** | Plusieurs liées à plusieurs, via une table de jointure |
| **Table de jointure (pivot)** | Table intermédiaire pour gérer le many-to-many |

### Divers

| Terme | Définition |
| --- | --- |
| **GROUP BY** | Regrouper des lignes pour agréger (COUNT, SUM...) |
| **HAVING** | Filtrer après un GROUP BY |
| **ORDER BY** | Trier les résultats |
| **DISTINCT** | Supprimer les doublons |
| **Index** | Structure pour accélérer les recherches |
| **Transaction** | Ensemble d'opérations exécutées "tout ou rien" |
| **COMMIT / ROLLBACK** | Valider / annuler une transaction |
| **Schéma** | Organisation logique des tables dans une base |

---

[![◀ Précédent](https://img.shields.io/badge/◀-Pr%C3%A9c%C3%A9dent-2E86AB?style=flat-square)](git-github.md)
[![🏠 Sommaire](https://img.shields.io/badge/🏠-Sommaire-555555?style=flat-square)](../README.md)
[![Suivant ▶](https://img.shields.io/badge/Suivant-%E2%96%B6-2E86AB?style=flat-square)](javascript.md)
```

- [ ] **Step 2: Vérifier le contenu**

Run: `grep -c "^### " vocabulaire-cda/sql-postgresql.md`
Expected: `4` (4 sous-sections : Commandes terminal, Langage SQL, Clés & contraintes, Relations & jointures... + Divers = vérifier que ça donne bien 5)

Note : recompter avant de valider — il y a 5 sous-titres `###` dans ce fichier (Commandes terminal `psql`, Langage SQL, Clés & contraintes, Relations & jointures, Divers). La commande doit donc renvoyer `5`.

Run: `grep -q "Précédent" vocabulaire-cda/sql-postgresql.md && echo OK`
Expected: `OK`

- [ ] **Step 3: Commit**

```bash
git add vocabulaire-cda/sql-postgresql.md
git commit -m "docs: extrait la section SQL/PostgreSQL dans vocabulaire-cda/sql-postgresql.md"
```

---

### Task 3: Créer `vocabulaire-cda/javascript.md`

**Files:**
- Create: `vocabulaire-cda/javascript.md`

**Interfaces:**
- Consumes: `sql-postgresql.md` (Task 2) comme cible du badge "◀ Précédent"
- Produces: fichier `vocabulaire-cda/javascript.md`, badges "◀ Précédent" → `sql-postgresql.md`, "Suivant ▶" → `css-themes.md`

- [ ] **Step 1: Créer le fichier avec le contenu déplacé + badges de navigation**

Créer `vocabulaire-cda/javascript.md` avec exactement ce contenu :

```markdown
# 🟨 JAVASCRIPT

### Bases

| Terme | Définition |
| --- | --- |
| `var` | Déclaration de variable (ancienne, portée fonction) — à éviter |
| `let` | Variable modifiable, portée bloc |
| `const` | Variable non réassignable, portée bloc |
| **Type primitif** | string, number, boolean, null, undefined, symbol, bigint |
| **Objet / Array** | Types complexes (collections de données) |
| `===` vs `==` | Égalité stricte (type + valeur) vs égalité "souple" (conversion de type) |
| **Template literals** | `` `Bonjour ${nom}` `` — chaînes avec variables intégrées |
| **Destructuring** | `const {a, b} = obj` — extraire des valeurs facilement |
| **Spread `...`** | Étaler un tableau/objet (`[...arr]`) |
| **Rest `...`** | Regrouper des arguments restants dans une fonction |
| **Scope (portée)** | Zone où une variable est accessible |
| **Hoisting** | Les déclarations sont "remontées" en haut du contexte à l'exécution |

### Fonctions

| Terme | Définition |
| --- | --- |
| **Function declaration** | `function nom() {}` — déclarée classiquement |
| **Function expression** | `const f = function() {}` — stockée dans une variable |
| **Arrow function** | `const f = () => {}` — syntaxe courte, sans son propre `this` |
| **Paramètre** | Variable définie dans la fonction |
| **Argument** | Valeur réellement passée à l'appel |
| `return` | Renvoie une valeur et arrête la fonction |
| **Callback** | Fonction passée en argument, appelée plus tard |
| **Closure** | Fonction qui garde accès aux variables de son contexte parent |
| **this** | Fait référence au contexte d'exécution courant |
| **Fonction anonyme** | Fonction sans nom |

### Conditions & boucles

| Terme | Définition |
| --- | --- |
| `if / else if / else` | Exécution conditionnelle |
| `switch` | Teste une valeur contre plusieurs cas (`case`) |
| `case` | Une valeur possible dans un switch |
| `break` | Arrête l'exécution du switch (évite de tomber dans le cas suivant) |
| `default` | Cas exécuté si aucun `case` ne correspond |
| `for` | Boucle classique avec compteur |
| `while` | Boucle tant qu'une condition est vraie |
| `for...of` | Boucle sur les valeurs d'un tableau/itérable |
| `for...in` | Boucle sur les clés d'un objet |

### Tableaux & objets

| Terme | Définition |
| --- | --- |
| `.map()` | Transforme chaque élément, renvoie un nouveau tableau |
| `.filter()` | Garde les éléments qui respectent une condition |
| `.reduce()` | Réduit le tableau à une seule valeur (ex: somme) |
| `.forEach()` | Exécute une action sur chaque élément (pas de retour) |
| `.find()` | Renvoie le premier élément correspondant |
| **Objet** | Collection de paires clé/valeur |
| **Méthode** | Fonction stockée dans un objet |

### Asynchrone

| Terme | Définition |
| --- | --- |
| **Promise** | Objet représentant une valeur future (résolue ou rejetée) |
| `async` | Marque une fonction comme asynchrone (renvoie une Promise) |
| `await` | Attend la résolution d'une Promise avant de continuer |
| `.then() / .catch()` | Gérer le succès / l'échec d'une Promise |
| **Event loop** | Mécanisme qui gère l'exécution asynchrone en JS |

---

[![◀ Précédent](https://img.shields.io/badge/◀-Pr%C3%A9c%C3%A9dent-2E86AB?style=flat-square)](sql-postgresql.md)
[![🏠 Sommaire](https://img.shields.io/badge/🏠-Sommaire-555555?style=flat-square)](../README.md)
[![Suivant ▶](https://img.shields.io/badge/Suivant-%E2%96%B6-2E86AB?style=flat-square)](css-themes.md)
```

- [ ] **Step 2: Vérifier le contenu**

Run: `grep -c "^### " vocabulaire-cda/javascript.md`
Expected: `5` (Bases, Fonctions, Conditions & boucles, Tableaux & objets, Asynchrone)

Run: `grep -q "Event loop" vocabulaire-cda/javascript.md && echo OK`
Expected: `OK`

- [ ] **Step 3: Commit**

```bash
git add vocabulaire-cda/javascript.md
git commit -m "docs: extrait la section JavaScript dans vocabulaire-cda/javascript.md"
```

---

### Task 4: Créer `vocabulaire-cda/css-themes.md`

**Files:**
- Create: `vocabulaire-cda/css-themes.md`

**Interfaces:**
- Consumes: `javascript.md` (Task 3) comme cible du badge "◀ Précédent"
- Produces: fichier `vocabulaire-cda/css-themes.md`, dernier maillon de la chaîne (pas de badge "Suivant ▶")

- [ ] **Step 1: Créer le fichier avec le contenu déplacé + badges de navigation**

Créer `vocabulaire-cda/css-themes.md` avec exactement ce contenu :

```markdown
# 🎨 CSS / THÈMES

### Variables CSS (custom properties)

| Terme | Définition |
| --- | --- |
| `:root` | Sélecteur ciblant la racine du document (`<html>`) — portée globale |
| `--nom-variable` | Déclare une variable CSS (custom property) |
| `var(--nom-variable)` | Utilise la valeur d'une variable CSS |
| `var(--nom, repli)` | Variable avec valeur de secours si elle n'est pas définie |
| **Custom property** | Nom technique des variables CSS ; suit les règles de cascade/héritage comme les autres propriétés |
| **Cascade / héritage** | Une variable définie sur `:root` est accessible partout, sauf si un sélecteur plus spécifique la redéfinit |

### Créer un thème (clair/sombre) dans `globals.css`

| Terme | Définition |
| --- | --- |
| `globals.css` | Fichier CSS global (souvent dans Next.js) où l'on définit `:root` et les styles de base |
| `:root { --bg: #fff; --text: #111; }` | Définit les valeurs par défaut (thème clair) |
| `[data-theme="dark"] { --bg: #111; --text: #fff; }` | Redéfinit les mêmes variables quand l'attribut est présent (thème sombre) |
| `@media (prefers-color-scheme: dark) { ... }` | Applique un thème selon la préférence système, en pur CSS |
| **Design token** | Nom donné aux variables qui représentent des choix de design (couleurs, espacements, rayons...) réutilisés dans toute l'app |

### Architecture à 3 fichiers (Exemple Dossier `/styles`)

Une architecture propre consiste à séparer le stockage du thème, la structure générale, et le point d'entrée global.

#### 1. `variables.css`
*Rôle : Stocke uniquement les Design Tokens (le dictionnaire des couleurs et thèmes).*

```css
/* Définition du thème par défaut (Clair) */
:root {
  --bg-primary: #ffffff;
  --bg-secondary: #f4f4f9;
  --text-main: #222222;
  --text-muted: #666666;
  --accent-color: #00b0f0;
}

/* Redéfinition pour le thème Sombre */
[data-theme="dark"] {
  --bg-primary: #121212;
  --bg-secondary: #1e1e1e;
  --text-main: #ffffff;
  --text-muted: #aaaaaa;
  --accent-color: #33c2ff;
}
```

---

[![◀ Précédent](https://img.shields.io/badge/◀-Pr%C3%A9c%C3%A9dent-2E86AB?style=flat-square)](javascript.md)
[![🏠 Sommaire](https://img.shields.io/badge/🏠-Sommaire-555555?style=flat-square)](../README.md)
```

- [ ] **Step 2: Vérifier le contenu**

Run: `grep -q "accent-color: #33c2ff" vocabulaire-cda/css-themes.md && echo OK`
Expected: `OK`

Run: `grep -c "Suivant" vocabulaire-cda/css-themes.md`
Expected: `0` (dernier fichier, pas de badge Suivant)

- [ ] **Step 3: Commit**

```bash
git add vocabulaire-cda/css-themes.md
git commit -m "docs: extrait la section CSS/Thèmes dans vocabulaire-cda/css-themes.md"
```

---

### Task 5: Réécrire `README.md`

**Files:**
- Modify: `README.md` (remplacement intégral du contenu actuel)

**Interfaces:**
- Consumes: les 4 fichiers créés dans les Tasks 1-4 (chemins `vocabulaire-cda/*.md`)
- Produces: `README.md` avec badges technos, table des matières, structure du projet, badge "Suivant ▶" vers `vocabulaire-cda/git-github.md`

- [ ] **Step 1: Remplacer le contenu de `README.md`**

Remplacer tout le contenu de `README.md` par :

```markdown
# Mémo Vocabulaire CDA

Mémo personnel de vocabulaire technique pour la formation Concepteur Développeur d'Applications (CDA) : Git/GitHub, SQL/PostgreSQL, JavaScript et CSS.

![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

## 📑 Table des matières

1. [🔧 Git / GitHub](vocabulaire-cda/git-github.md)
2. [🗄️ SQL / PostgreSQL](vocabulaire-cda/sql-postgresql.md)
3. [🟨 JavaScript](vocabulaire-cda/javascript.md)
4. [🎨 CSS / Thèmes](vocabulaire-cda/css-themes.md)

## 📂 Structure du projet

```text
memoVocab-cda/
├── README.md
└── vocabulaire-cda/
    ├── git-github.md
    ├── sql-postgresql.md
    ├── javascript.md
    └── css-themes.md
```

---

[![Suivant ▶](https://img.shields.io/badge/Suivant-%E2%96%B6-2E86AB?style=flat-square)](vocabulaire-cda/git-github.md)
```

- [ ] **Step 2: Vérifier le contenu**

Run: `grep -c "vocabulaire-cda/" README.md`
Expected: `5` (4 liens de la table des matières + 1 badge Suivant)

Run: `grep -q "🔧 GIT" README.md || echo "OK - ancien contenu retiré"`
Expected: `OK - ancien contenu retiré` (le tableau Git ne doit plus être dans le README, seulement dans `vocabulaire-cda/git-github.md`)

- [ ] **Step 3: Commit**

```bash
git add README.md
git commit -m "docs: transforme le README en page d'accueil avec table des matières et badges"
```

---

### Task 6: Vérification finale des liens et du contenu

**Files:**
- None (vérification uniquement)

**Interfaces:**
- Consumes: tous les fichiers des Tasks 1-5

- [ ] **Step 1: Vérifier que tous les fichiers cibles des liens existent**

Run (PowerShell) :
```powershell
foreach ($f in @("vocabulaire-cda/git-github.md","vocabulaire-cda/sql-postgresql.md","vocabulaire-cda/javascript.md","vocabulaire-cda/css-themes.md")) {
  if (-not (Test-Path $f)) { Write-Output "MANQUANT: $f" } else { Write-Output "OK: $f" }
}
```
Expected: 4 lignes `OK: ...`, aucune ligne `MANQUANT`

- [ ] **Step 2: Vérifier qu'aucune ligne de tableau du vocabulaire d'origine n'a été perdue**

Run: `(Get-Content vocabulaire-cda/git-github.md, vocabulaire-cda/sql-postgresql.md, vocabulaire-cda/javascript.md, vocabulaire-cda/css-themes.md | Select-String "^\|").Count`
Expected: `146` (nombre total de lignes de tableau `| ... |`, en-têtes et séparateurs inclus, mesuré sur le `README.md` d'origine avec `grep -c "^|" README.md` avant migration — doit être identique une fois le contenu réparti dans les 4 fichiers)

- [ ] **Step 3: Vérifier visuellement le rendu**

Ouvrir `README.md` et chaque fichier de `vocabulaire-cda/` dans l'aperçu markdown de l'éditeur (ou GitHub une fois poussé) pour confirmer que les badges s'affichent et que les liens de navigation pointent au bon endroit.

---

### Task 7: Nettoyage du dossier `docs/`

**Files:**
- Delete: `docs/superpowers/specs/2026-07-07-vocabulaire-cda-docs-restructure-design.md`
- Delete: `docs/superpowers/plans/2026-07-07-vocabulaire-cda-docs-restructure.md` (ce plan lui-même)
- Delete: dossier `docs/` dans son ensemble une fois vide

**Interfaces:**
- Consumes: rien (nettoyage final, exécuté uniquement après validation de la Task 6)

- [ ] **Step 1: Supprimer le dossier `docs/`**

```bash
git rm -r docs/
```

- [ ] **Step 2: Vérifier qu'il ne reste plus rien**

Run: `git status`
Expected: `docs/` n'apparaît plus dans l'arborescence du dépôt (fichiers supprimés listés en staged deletion avant le commit)

- [ ] **Step 3: Commit**

```bash
git commit -m "chore: supprime les artefacts de planification (docs/) une fois la migration validée"
```
