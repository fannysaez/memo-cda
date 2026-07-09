# 🟨 JavaScript

### Bases

| Terme                 | Définition                                                               |
| --------------------- | ------------------------------------------------------------------------ |
| `var`                 | Déclaration de variable (ancienne, portée fonction) — à éviter           |
| `let`                 | Variable modifiable, portée bloc                                         |
| `const`               | Variable non réassignable, portée bloc                                   |
| **Type primitif**     | string, number, boolean, null, undefined, symbol, bigint                 |
| **Objet / Array**     | Types complexes (collections de données)                                 |
| `===` vs `==`         | Égalité stricte (type + valeur) vs égalité "souple" (conversion de type) |
| **Template literals** | `` `Bonjour ${nom}` `` — chaînes avec variables intégrées                |
| **Destructuring**     | `const {a, b} = obj` — extraire des valeurs facilement                   |
| **Spread `...`**      | Étaler un tableau/objet (`[...arr]`)                                     |
| **Rest `...`**        | Regrouper des arguments restants dans une fonction                       |
| **Scope (portée)**    | Zone où une variable est accessible                                      |
| **Hoisting**          | Les déclarations sont "remontées" en haut du contexte à l'exécution      |

### Fonctions

| Terme                    | Définition                                                    |
| ------------------------ | ------------------------------------------------------------- |
| **Function declaration** | `function nom() {}` — déclarée classiquement                  |
| **Function expression**  | `const f = function() {}` — stockée dans une variable         |
| **Arrow function**       | `const f = () => {}` — syntaxe courte, sans son propre `this` |
| **Paramètre**            | Variable définie dans la fonction                             |
| **Argument**             | Valeur réellement passée à l'appel                            |
| `return`                 | Renvoie une valeur et arrête la fonction                      |
| **Callback**             | Fonction passée en argument, appelée plus tard                |
| **Closure**              | Fonction qui garde accès aux variables de son contexte parent |
| **this**                 | Fait référence au contexte d'exécution courant                |
| **Fonction anonyme**     | Fonction sans nom                                             |

### Conditions & boucles

| Terme                 | Définition                                                         |
| --------------------- | ------------------------------------------------------------------ |
| `if / else if / else` | Exécution conditionnelle                                           |
| `switch`              | Teste une valeur contre plusieurs cas (`case`)                     |
| `case`                | Une valeur possible dans un switch                                 |
| `break`               | Arrête l'exécution du switch (évite de tomber dans le cas suivant) |
| `default`             | Cas exécuté si aucun `case` ne correspond                          |
| `for`                 | Boucle classique avec compteur                                     |
| `while`               | Boucle tant qu'une condition est vraie                             |
| `for...of`            | Boucle sur les valeurs d'un tableau/itérable                       |
| `for...in`            | Boucle sur les clés d'un objet                                     |

### Tableaux & objets

| Terme        | Définition                                            |
| ------------ | ----------------------------------------------------- |
| `.map()`     | Transforme chaque élément, renvoie un nouveau tableau |
| `.filter()`  | Garde les éléments qui respectent une condition       |
| `.reduce()`  | Réduit le tableau à une seule valeur (ex: somme)      |
| `.forEach()` | Exécute une action sur chaque élément (pas de retour) |
| `.find()`    | Renvoie le premier élément correspondant              |
| **Objet**    | Collection de paires clé/valeur                       |
| **Méthode**  | Fonction stockée dans un objet                        |

### Asynchrone

| Terme                | Définition                                                 |
| -------------------- | ---------------------------------------------------------- |
| **Promise**          | Objet représentant une valeur future (résolue ou rejetée)  |
| `async`              | Marque une fonction comme asynchrone (renvoie une Promise) |
| `await`              | Attend la résolution d'une Promise avant de continuer      |
| `.then() / .catch()` | Gérer le succès / l'échec d'une Promise                    |
| **Event loop**       | Mécanisme qui gère l'exécution asynchrone en JS            |

***

<p align="center"><a href="sql-postgresql.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a>    <a href="css-themes.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a></p>
