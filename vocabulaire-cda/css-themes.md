# 🎨 CSS / Thèmes

### Variables CSS (custom properties)

| Terme                  | Définition                                                                                                 |
| ---------------------- | ---------------------------------------------------------------------------------------------------------- |
| `:root`                | Sélecteur ciblant la racine du document (`<html>`) — portée globale                                        |
| `--nom-variable`       | Déclare une variable CSS (custom property)                                                                 |
| `var(--nom-variable)`  | Utilise la valeur d'une variable CSS                                                                       |
| `var(--nom, repli)`    | Variable avec valeur de secours si elle n'est pas définie                                                  |
| **Custom property**    | Nom technique des variables CSS ; suit les règles de cascade/héritage comme les autres propriétés          |
| **Cascade / héritage** | Une variable définie sur `:root` est accessible partout, sauf si un sélecteur plus spécifique la redéfinit |

### Créer un thème (clair/sombre) dans `globals.css`

| Terme                                               | Définition                                                                                                                  |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `globals.css`                                       | Fichier CSS global (souvent dans Next.js) où l'on définit `:root` et les styles de base                                     |
| `:root { --bg: #fff; --text: #111; }`               | Définit les valeurs par défaut (thème clair)                                                                                |
| `[data-theme="dark"] { --bg: #111; --text: #fff; }` | Redéfinit les mêmes variables quand l'attribut est présent (thème sombre)                                                   |
| `@media (prefers-color-scheme: dark) { ... }`       | Applique un thème selon la préférence système, en pur CSS                                                                   |
| **Design token**                                    | Nom donné aux variables qui représentent des choix de design (couleurs, espacements, rayons...) réutilisés dans toute l'app |

### Architecture à 3 fichiers (Exemple Dossier `/styles`)

Une architecture propre consiste à séparer le stockage du thème, la structure générale, et le point d'entrée global.

#### 1. `variables.css`

_Rôle : Stocke uniquement les Design Tokens (le dictionnaire des couleurs et thèmes)._

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

***

<p align="center"><a href="javascript.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a>    <a href="bootstrap.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a></p>
