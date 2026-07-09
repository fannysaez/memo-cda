# 🅱️ BOOTSTRAP

### Intégration

| Terme | Définition |
| --- | --- |
| **CDN** | Lien vers le CSS/JS de Bootstrap hébergé en ligne, sans installation |
| `npm install bootstrap` | Installe Bootstrap en local (via un gestionnaire de paquets) |
| `container` | Bloc centré avec marges fixes selon la taille d'écran |
| `container-fluid` | Bloc qui occupe toute la largeur disponible |

### Système de grille (Grid)

| Terme | Définition |
| --- | --- |
| **Grid system** | Système de mise en page basé sur 12 colonnes |
| `row` | Conteneur horizontal qui regroupe des colonnes |
| `col` | Colonne qui se partage l'espace disponible avec les autres |
| `col-6` | Colonne occupant 6/12 de la largeur (soit 50%) |
| `col-md-4` | Colonne occupant 4/12 à partir du breakpoint `md` |
| `offset-2` | Décale une colonne de 2 unités vers la droite |
| `g-3` | Gouttière (gap) entre les colonnes/lignes |

### Breakpoints (responsive)

| Terme | Définition |
| --- | --- |
| `sm` | ≥ 576px (petits écrans) |
| `md` | ≥ 768px (tablettes) |
| `lg` | ≥ 992px (petits écrans de bureau) |
| `xl` | ≥ 1200px (grands écrans) |
| `xxl` | ≥ 1400px (très grands écrans) |
| **Mobile first** | Approche où les styles de base ciblent le mobile, puis sont adaptés vers le haut avec les breakpoints |

### Utilitaires (Utilities)

| Terme | Définition |
| --- | --- |
| `d-flex` | Applique `display: flex` |
| `d-none` | Masque l'élément (`display: none`) |
| `m-3`, `p-3` | Marge (`margin`) / espacement interne (`padding`), échelle de 0 à 5 |
| `mt-2`, `mb-2`, `mx-auto` | Marge ciblée (top, bottom, horizontale centrée) |
| `text-center` | Centre le texte |
| `justify-content-between` | Répartit les éléments flex avec espace entre eux |
| `align-items-center` | Centre verticalement les éléments flex |
| `w-100` | Largeur à 100% |

### Composants courants

| Terme | Définition |
| --- | --- |
| `navbar` | Barre de navigation responsive |
| `card` | Bloc de contenu encadré (titre, texte, image, actions) |
| `btn` / `btn-primary` | Bouton stylisé / variante de couleur |
| `modal` | Fenêtre superposée (popup) |
| `alert` / `alert-danger` | Message d'information ou d'erreur mis en avant |
| `badge` | Petite étiquette (compteur, statut) |
| `dropdown` | Menu déroulant |
| `carousel` | Diaporama d'images ou de contenus |

### Formulaires

| Terme | Définition |
| --- | --- |
| `form-control` | Style standard pour les champs `input`, `textarea`, `select` |
| `form-label` | Style pour les labels de formulaire |
| `form-check` | Style pour les cases à cocher / boutons radio |
| `is-invalid` / `is-valid` | Classes indiquant un champ invalide / valide |
| `invalid-feedback` | Message d'erreur affiché sous un champ invalide |

### JavaScript / Data attributes

| Terme | Définition |
| --- | --- |
| `data-bs-toggle="modal"` | Déclenche l'ouverture d'un composant (modal, dropdown...) sans écrire de JS |
| `data-bs-target="#id"` | Cible l'élément concerné par l'action (ex : la modale à ouvrir) |
| `data-bs-dismiss="modal"` | Ferme la modale au clic |
| **Bundle JS** | Fichier `bootstrap.bundle.min.js` incluant Popper.js (nécessaire pour dropdowns, tooltips...) |

---

<p align="center">
  <a href="css-themes.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="tailwindcss.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a>
</p>
