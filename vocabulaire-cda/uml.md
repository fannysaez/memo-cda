# 📐 UML

### Bases

| Terme | Définition |
| --- | --- |
| **UML** | *Unified Modeling Language* (Langage de Modélisation Unifiée) — langage graphique pour représenter la structure d'un système informatique |
| **Diagramme structurel** | Représente les éléments statiques d'un système (amenés à rester fixes) et les liens entre eux |
| **Diagramme comportemental** | Représente les actions entre différents éléments et leur évolution dans le temps |
| **13 types de diagrammes** | UML compte 13 types de diagrammes répartis entre structurels et comportementaux |

### Diagramme de cas d'utilisation

| Terme | Définition |
| --- | --- |
| **Diagramme de cas d'utilisation** | Diagramme comportemental établissant ce que le système doit faire (actions), du point de vue de l'utilisateur — répond à "Que fait le système ?" |
| **Acteur** | Utilisateur (ou système externe) qui interagit avec le système |
| **Cas d'utilisation (use case)** | Une action/fonctionnalité que le système propose à un acteur |
| `Include` | "Ce cas d'utilisation *nécessite* ce cas-ci" — l'un ne peut pas se produire sans l'autre |
| `Extend` | Un cas d'utilisation peut en déclencher un autre sous certaines conditions |
| **Héritage entre acteurs** | Un acteur spécifique hérite des cas d'utilisation d'un acteur plus général |

### Diagramme de classes

| Terme | Définition |
| --- | --- |
| **Diagramme de classes** | Modélise les objets d'un système : classes, attributs, méthodes, relations et héritage |
| **Classe (UML)** | Rectangle en 3 parties : nom (`PascalCase`), attributs (`camelCase`), méthodes (`camelCase`) |
| `+` | Visibilité **public** — accessible en dehors de la classe |
| `-` | Visibilité **private** — accessible uniquement dans la classe |
| `#` | Visibilité **protected** — accessible aussi dans les classes filles |
| **Identifiant** | Attribut unique qui repère un objet précis parmi les autres (ex : `idClient`) |
| **Association** | Ligne simple entre deux classes : elles se connaissent mais restent indépendantes |
| **Généralisation (héritage)** | Flèche triangulaire de la classe fille vers la classe parente |
| **Multiplicité** | Indique combien d'objets sont concernés de chaque côté d'une relation (`1`, `0..1`, `0..*`, `1..*`) |
| **Agrégation (◇)** | "A un" — lien faible ; l'objet contenu peut exister sans le conteneur (ex : étudiant/université) |
| **Composition (◆)** | "A un" — lien fort ; si le conteneur est supprimé, l'objet contenu l'est aussi (ex : pièce/maison) |

### Diagramme de séquence

| Terme | Définition |
| --- | --- |
| **Diagramme de séquence** | Montre les échanges de messages entre objets, dans l'ordre chronologique — met l'accent sur le temps |
| **Ligne de vie** | Ligne verticale représentant un objet ou composant du système |
| **Barre d'activation** | Montre la durée pendant laquelle un objet est actif |
| **Message** | Flèche entre deux lignes de vie représentant une interaction |
| `alt` (alternative) | Choix entre plusieurs séquences d'interactions (comme un if/else) |
| `opt` (optionnel) | Séquence qui peut se produire ou non (comme un if sans else) |
| `loop` (boucle) | Séquence qui se répète (comme un while/for) |
| `par` (parallèle) | Séquences qui s'exécutent en parallèle |
| `ref` (référence) | Renvoie vers un autre diagramme de séquence, pour éviter la duplication |
| `break` | Sortie anticipée d'une boucle |
| `critical` | Section critique |

### Diagramme d'activités

| Terme | Définition |
| --- | --- |
| **Diagramme d'activités** | Diagramme comportemental représentant un flux (workflow) d'actions et d'événements, proche d'un organigramme |
| **Nœud initial (⬤)** | Point de départ du flux |
| **Nœud final (◉)** | Point de fin du flux |
| **Nœud de décision (◇)** | Représente un choix, une condition (if/else) |
| **Nœud de bifurcation/union (▬)** | Sépare ou rassemble des flux en parallèle (fork/join) |
| **Nœud d'objet (▭)** | Permet de passer des données d'une activité à une autre |
| **Nœud d'action (⬭)** | Représente l'exécution d'une action |

---

<p align="center">
  <a href="php.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="poo.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a>
</p>
