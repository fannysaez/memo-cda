# 🌊 TAILWIND CSS

### Intégration

| Terme | Définition |
| --- | --- |
| **Utility-first** | Approche où le style se construit en combinant des classes utilitaires directement dans le HTML, sans écrire de CSS custom |
| **Play CDN** | `<script src="https://cdn.tailwindcss.com"></script>` — teste Tailwind sans installation (déconseillé en production) |
| `npm install tailwindcss` | Installe Tailwind en local (via un gestionnaire de paquets) |
| `@import "tailwindcss";` | Directive (v4) qui injecte les styles de base, composants et utilitaires dans le CSS |
| `tailwind.config.js` | Fichier de configuration (thème, couleurs, breakpoints, plugins) |
| **JIT (Just-In-Time)** | Moteur qui génère à la volée uniquement les classes réellement utilisées dans le code |

### Mise en page (Layout)

| Terme | Définition |
| --- | --- |
| `flex` | Applique `display: flex` |
| `grid` | Applique `display: grid` |
| `grid-cols-3` | Grille à 3 colonnes de largeur égale |
| `col-span-2` | Élément qui occupe 2 colonnes |
| `hidden` | Masque l'élément (`display: none`) |
| `block` / `inline-block` | Applique `display: block` / `inline-block` |
| `container` | Bloc dont la largeur max s'adapte aux breakpoints |

### Espacement (Spacing)

| Terme | Définition |
| --- | --- |
| `p-4` | Padding sur les 4 côtés (échelle en `rem`, ex : `4` = 1rem) |
| `px-4`, `py-2` | Padding horizontal / vertical |
| `m-4`, `mx-auto` | Margin sur les 4 côtés / margin horizontale centrée |
| `mt-2`, `mb-2` | Margin ciblée (top, bottom) |
| `gap-4` | Espacement entre les enfants d'un `flex` ou `grid` |
| `w-full`, `h-screen` | Largeur à 100% / hauteur égale à celle de l'écran |

### Flexbox & alignement

| Terme | Définition |
| --- | --- |
| `justify-center` | Centre les éléments sur l'axe principal (horizontal par défaut) |
| `justify-between` | Répartit les éléments avec de l'espace entre eux |
| `items-center` | Centre les éléments sur l'axe secondaire (vertical par défaut) |
| `flex-col` | Change la direction du flex en colonne |
| `flex-wrap` | Autorise le retour à la ligne des éléments |
| `flex-1` | Élément qui grandit/rétrécit pour occuper l'espace disponible |

### Typographie & couleurs

| Terme | Définition |
| --- | --- |
| `text-xl`, `text-2xl` | Taille de police (échelle prédéfinie) |
| `font-bold`, `font-medium` | Graisse de la police |
| `text-center` | Centre le texte |
| `text-gray-500` | Couleur du texte (palette + nuance de 50 à 950) |
| `bg-blue-600` | Couleur de fond |
| `border`, `border-gray-300` | Bordure / couleur de bordure |
| `rounded-lg` | Coins arrondis |
| `shadow-md` | Ombre portée |

### Responsive (breakpoints)

| Terme | Définition |
| --- | --- |
| **Mobile first** | Les classes sans préfixe ciblent le mobile ; les préfixes appliquent le style à partir du breakpoint indiqué |
| `sm:` | ≥ 640px |
| `md:` | ≥ 768px |
| `lg:` | ≥ 1024px |
| `xl:` | ≥ 1280px |
| `2xl:` | ≥ 1536px |
| `md:flex-row` | Exemple : passe en `flex-row` à partir de `md` |

### États & variantes

| Terme | Définition |
| --- | --- |
| `hover:bg-blue-700` | Style appliqué au survol de la souris |
| `focus:ring-2` | Style appliqué quand l'élément a le focus (ex : anneau visible) |
| `disabled:opacity-50` | Style appliqué quand l'élément est désactivé |
| `dark:bg-gray-900` | Style appliqué quand le mode sombre est actif |
| `group` / `group-hover:` | Applique un style à un enfant selon l'état survolé du parent |
| `active:scale-95` | Style appliqué pendant le clic/l'activation |

### Personnalisation

| Terme | Définition |
| --- | --- |
| `@theme` | Directive (v4) pour définir des tokens de design (couleurs, polices...) directement en CSS |
| `@apply` | Regroupe plusieurs classes utilitaires dans une classe CSS custom |
| **Arbitrary values** | Valeur ponctuelle hors échelle, ex : `w-[137px]`, `bg-[#1da1f2]` |
| `theme()` | Fonction pour réutiliser une valeur du thème dans du CSS custom |

Exemple de thème custom déclaré avec la Play CDN (`<style type="text/tailwindcss">`) :

```html
<style type="text/tailwindcss">
  @theme {
    --color-ink: #2b1810;
    --color-cocoa: #4a2c1d;
    --color-rose: #9B3F59;
    --color-sage: #a67c52;
    --color-gold: #c9974c;
    --color-cream: #f5e6d3;
    --color-mist: #ede1d1;
    --color-page: #fdf8f0;
    --font-display: "Poppins", sans-serif;
    --font-sans: "Inter", sans-serif;
  }
</style>
```

Chaque `--color-nom` et `--font-nom` génère automatiquement les classes utilitaires correspondantes (`bg-ink`, `text-rose`, `border-sage`, `font-display`...), utilisables partout dans le HTML comme les couleurs par défaut de Tailwind.

### Images

| Terme | Définition |
| --- | --- |
| `picsum.photos/seed/nom/800/600` | Service générant une image placeholder aléatoire mais reproductible (même seed = même image), pratique pour prototyper |
| **WebP** | Format d'image compressé plus léger que JPEG/PNG, recommandé pour la performance (conversion via un outil comme Squoosh, `sharp`, ou le build) |
| `opacity-0` | Rend l'image invisible tant qu'elle n'est pas chargée |
| `transition-opacity duration-700` | Anime en fondu (fade-in) l'apparition de l'opacité sur 700ms |
| **Fade-in au chargement** | Technique : l'image démarre en `opacity-0`, puis un script bascule sur `opacity-100` à l'événement `load` de l'image |

```html
<img
  id="hero-image"
  src="https://picsum.photos/seed/chocolatier/800/600"
  alt="Chocolatier Bakery"
  class="w-full h-full object-cover rounded-2xl shadow-2xl opacity-0 transition-opacity duration-700"
/>
```

### Navigation responsive (menu burger)

| Terme | Définition |
| --- | --- |
| `hidden md:flex` | Masque la nav sur mobile, l'affiche en `flex` à partir du breakpoint `md` (nav desktop) |
| `md:hidden` | Affiche un élément uniquement en dessous de `md` (bouton burger mobile) |
| `aria-label`, `aria-expanded`, `aria-controls` | Attributs d'accessibilité : nom du bouton, état ouvert/fermé, id de l'élément contrôlé |
| `&#9776;` | Entité HTML de l'icône hamburger (☰) |
| **Toggle JS** | Script qui écoute le clic sur le bouton burger et bascule la classe `hidden` (+ `flex`) sur le menu mobile |

```html
<nav class="hidden md:flex items-center gap-8 text-sm text-ink/70">
  <a href="#menu" class="hover:text-ink">Menu</a>
  <a href="#story" class="hover:text-ink">Our Story</a>
  <a href="#order" class="hover:text-ink">Order</a>
  <a href="#contact" class="hover:text-ink">Contact</a>
</nav>
<button
  id="menu-toggle"
  class="md:hidden w-9 h-9 rounded-full border border-ink/10 flex items-center justify-center text-ink"
  aria-label="Menu"
  aria-expanded="false"
  aria-controls="mobile-menu"
>
  &#9776;
</button>

<nav
  id="mobile-menu"
  class="hidden md:hidden flex-col items-center gap-4 text-sm text-ink/70 mt-4 pt-4 border-t border-ink/10"
>
  <a href="#menu" class="hover:text-ink">Menu</a>
  <a href="#story" class="hover:text-ink">Our Story</a>
  <a href="#order" class="hover:text-ink">Order</a>
  <a href="#contact" class="hover:text-ink">Contact</a>
</nav>
```

### Déploiement

| Terme | Définition |
| --- | --- |
| **Vercel** | Plateforme qui build et déploie automatiquement un site à chaque push sur le dépôt relié |
| **GitHub Pages** | Hébergement statique gratuit servi directement depuis un dépôt GitHub (branche dédiée ou dossier `/docs`) |
| **Preview deployment** | URL temporaire générée par Vercel pour chaque branche/PR, avant la mise en production |

Exemple perso ([chocolatierBakery-restaurant](https://github.com/fannysaez/chocolatierBakery-restaurant)) déployé sur les deux plateformes :

- Vercel : [chocolatier-bakery-restaurant.vercel.app](https://chocolatier-bakery-restaurant.vercel.app/)
- GitHub Pages : [fannysaez.github.io/chocolatierBakery-restaurant](https://fannysaez.github.io/chocolatierBakery-restaurant/)

---

<p align="center">
  <a href="bootstrap.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="../README.md"><img src="https://img.shields.io/badge/-RETOUR-2E86AB?style=for-the-badge" alt="Retour"></a>
</p>
