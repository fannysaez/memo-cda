# 🔷 TypeScript

### Bases

| Terme | Définition |
| --- | --- |
| **Langage haut niveau** | Langage de programmation proche du langage humain, plus facile à lire/écrire, mais devant être traduit avant exécution (ex : TypeScript, JavaScript, Python) |
| **TypeScript** | Sur-ensemble de JavaScript développé par Microsoft, qui ajoute un système de **typage statique optionnel** — détecte des erreurs dès l'écriture plutôt qu'à l'exécution |
| **Transpiler / Transpilation** | Traduire du code source vers un langage de niveau équivalent (contrairement à un compilateur classique qui traduit vers du plus bas niveau) — `npx tsc` transpile les `.ts` en `.js` |
| `interface` | Définit la forme attendue d'un objet (propriétés obligatoires et leurs types), pour que TypeScript vérifie la cohérence du code |
| `void` | Type indiquant qu'une fonction ne renvoie rien |
| `string \| null` | Type "union" — la valeur peut être soit une chaîne, soit `null` (le `\|` signifie "ou bien") |
| **Template literal** | Chaîne délimitée par des backticks `` ` `` permettant d'insérer des variables avec `${...}` |
| `tsconfig.json` | Fichier de configuration du compilateur TypeScript (généré par `npx tsc --init`) |
| `"outDir"` | Option de `tsconfig.json` indiquant le dossier où placer les fichiers compilés (ex : `dist/`) |
| `"target"` | Option de `tsconfig.json` définissant la version de JavaScript vers laquelle TypeScript compile |

### Environnement / outillage

| Terme | Définition |
| --- | --- |
| **Node.js** | Environnement d'exécution (*runtime*) permettant d'exécuter du JavaScript en dehors d'un navigateur (terminal, serveur) |
| **Gestionnaire de package** | Outil qui automatise l'installation, la mise à jour et la suppression des dépendances d'un projet |
| **npm** *(Node Package Manager)* | Gestionnaire de packages installé par défaut avec Node.js (`npm install`, `npm init`, `npm run`) |
| **npx** *(Node Package eXecute)* | Outil fourni avec npm permettant d'exécuter directement un package sans l'installer globalement (ex : `npx tsc`) |
| **Yarn** | Gestionnaire de packages alternatif à npm, créé par Facebook |
| **Bun** | Runtime JavaScript/TypeScript tout-en-un (alternative à Node.js) embarquant son propre gestionnaire de packages, bundler et outil de test |
| **Watch mode** | Mode de compilation automatique qui recompile à chaque modification (`npx tsc --watch`) |

### Asynchrone (Promises, fetch)

| Terme | Définition |
| --- | --- |
| **Promesse (`Promise`)** | "Ticket d'attente" représentant un résultat qui arrivera plus tard (succès ou échec) |
| `fetch` | Fonction qui envoie une requête HTTP et renvoie une promesse, sans bloquer le programme |
| `.then()` | "Quand cette promesse est prête, fais ceci" — permet d'enchaîner les traitements |
| `.catch()` | "Si une erreur survient dans la chaîne de `.then()`, fais ceci à la place" |
| `async` | Mot-clé qui transforme une fonction pour pouvoir utiliser `await` à l'intérieur |
| `await` | Met en pause l'exécution de la fonction jusqu'à ce que la promesse soit résolue, puis donne le résultat directement |
| `try / catch` | "Essaie ce bloc, et si ça plante, exécute le bloc `catch` à la place" |
| `.then()` vs `async/await` | Deux syntaxes équivalentes : `.then()` enchaîne des blocs, `async/await` se lit comme du code séquentiel classique |

---

<p align="center">
  <a href="poo.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="angular.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a>
</p>
