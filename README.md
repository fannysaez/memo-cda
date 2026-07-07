# Mémo Vocabulaire CDA

## 🔧 GIT / GITHUB

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

## 🗄️ SQL / POSTGRESQL (terminal `psql`)

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

## 🟨 JAVASCRIPT

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

## 🎨 CSS / THÈMES

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