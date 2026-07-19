# 🅰️ Angular

### Bases

| Terme | Définition |
| --- | --- |
| **Angular** | Framework front-end open source, développé par Google, basé sur TypeScript — fournit une structure complète (composants, routage, formulaires, HTTP, DI) |
| **Framework vs bibliothèque** | Une bibliothèque (jQuery) laisse le développeur décider quand/comment l'utiliser ; un framework (Angular) impose sa propre structure de code |
| **SPA** *(Single Page Application)* | Application web qui se charge une seule fois puis met à jour dynamiquement son contenu, sans recharger la page entière |
| **Angular CLI** (`ng`) | Outil en ligne de commande officiel pour créer, développer, tester et builder des projets Angular |
| `ng new <nom>` | Crée un nouveau projet Angular (standalone, sans NgModules, par défaut depuis Angular 17+) |
| `ng serve` | Lance le serveur de développement (avec live reload) sur `localhost:4200` |
| `ng generate component <nom>` (`ng g c`) | Génère un nouveau composant |
| `ng generate service <nom>` (`ng g s`) | Génère un nouveau service |
| `ng build` | Compile l'application pour la production (dossier `dist/`) |
| `main.ts` | Point d'entrée qui démarre l'application via `bootstrapApplication(App, appConfig)` |
| `app.config.ts` | Centralise les *providers* globaux (routeur, client HTTP, etc.) |

### Composants

| Terme | Définition |
| --- | --- |
| **Composant** | Brique d'interface réutilisable qui contrôle une portion de l'écran — regroupe une classe TypeScript (logique), un template (HTML) et des styles (CSS) |
| **Template** | Le HTML qui décrit l'affichage d'un composant (en ligne via `template`, ou séparé via `templateUrl`) |
| **Signal** (`signal()`) | Conteneur de valeur réactif qui notifie automatiquement Angular quand elle change, pour que le template se mette à jour tout seul |
| `.set()` / `.update()` | Modifient la valeur d'un signal (valeur directe ou fonction basée sur la valeur actuelle) |
| **Composition de composants** | Un composant utilise un autre dans son template, en l'important dans le tableau `imports` |
| **Interpolation** (`{{ }}`) | Insère la valeur d'une expression/signal sous forme de texte dans le template |
| `@if` / `@else if` / `@else` | Nouvelle syntaxe de *control flow* (Angular 17+) pour afficher conditionnellement une portion de template — remplace `*ngIf` |
| `@for` / `track` / `@empty` | Itère sur une collection ; `track` fournit une clé stable indispensable aux performances ; `@empty` s'affiche si la collection est vide — remplace `*ngFor` |
| **Liaison de propriété** (`[propriété]="expression"`) | Lie dynamiquement un attribut/propriété DOM à une valeur de la classe (ex : `[disabled]`, `[src]`) |
| **Liaison d'événement** (`(événement)="expression"`) | Écoute un événement DOM et exécute du code en réponse ; l'objet natif est accessible via `$event` |
| `input()` / `input.required<T>()` | Déclare une propriété d'entrée permettant à un parent de transmettre des données à un composant enfant (optionnelle / obligatoire) |
| `output()` / `.emit()` | Déclare une propriété de sortie permettant à un enfant d'émettre un événement vers son parent |
| `@defer` | Diffère le chargement d'une partie du template jusqu'à une condition (clic, `on viewport`, délai...) — réduit la taille du bundle initial |
| `@placeholder` / `@loading` / `@error` | Blocs complémentaires de `@defer` : contenu avant déclenchement / pendant chargement / en cas d'échec |
| `NgOptimizedImage` (`ngSrc`) | Directive qui remplace `src` et applique automatiquement lazy loading, `srcset` responsive et préchargement (`priority`) |

### Routage

| Terme | Définition |
| --- | --- |
| `provideRouter()` | Fournit le routeur Angular (`@angular/router`) à l'application, dans `app.config.ts` |
| `<router-outlet>` | Emplacement réservé où le composant de la route active est inséré |
| **Route** | Association d'un `path` (chemin d'URL) à un `component`, définie dans un tableau `Routes` (`app.routes.ts`) |
| `path: ''` | Route par défaut (racine du site) |
| `path: '**'` | Route "wildcard" qui capture toutes les URL non reconnues (page 404) |
| `routerLink` | Directive qui remplace `href` pour naviguer entre routes sans recharger la page |
| `routerLinkActive` | Applique une classe CSS au lien correspondant à la route active |

### Formulaires

| Terme | Définition |
| --- | --- |
| `FormsModule` / `ngModel` | Approche template-driven : crée une liaison bidirectionnelle entre un champ et une propriété de la classe |
| `[(ngModel)]` *(banana in a box)* | Combine property binding (`[ngModel]`) et event binding (`(ngModelChange)`) |
| **Liaison bidirectionnelle** *(two-way binding)* | La propriété se met à jour quand l'utilisateur tape, et le champ se met à jour si la propriété change dans le code |
| `$event.target` | Accès direct à la valeur d'un champ via l'événement DOM natif (`(input)`, `(change)`), sans `ngModel` |
| `ReactiveFormsModule` | Formulaires réactifs : déplace la logique du formulaire dans la classe TypeScript plutôt que le template |
| `FormGroup` / `FormControl` | Modélisent un formulaire réactif (groupe de champs / champ individuel) avec typage fort |
| `Validators.required` / `.email` / `.minLength` | Validateurs intégrés associés à un `FormControl` |
| `valid` / `invalid` / `touched` / `dirty` | États d'un formulaire réactif, utilisés pour afficher des erreurs ciblées ou désactiver la soumission |

### Services & injection de dépendances

| Terme | Définition |
| --- | --- |
| **Service** | Classe TypeScript décorée `@Injectable()`, qui contient de la logique/données réutilisables (indépendante de tout composant) |
| `providedIn: 'root'` | Enregistre le service au niveau racine : Angular crée une instance unique partagée (singleton) entre tous les composants |
| **Injection de dépendances (DI)** | Mécanisme par lequel Angular fournit automatiquement une instance de service à qui en a besoin |
| `inject()` | Fonction moderne pour injecter un service dans un composant (remplace l'injection par constructeur) |

### Pipes

| Terme | Définition |
| --- | --- |
| **Pipe** | Fonction de transformation utilisable dans un template (`{{ valeur \| nomDuPipe }}`) sans modifier la donnée d'origine |
| `DatePipe` / `CurrencyPipe` / `UpperCasePipe` / `DecimalPipe` | Pipes intégrés (format de date, devise, casse, nombre) — doivent être importés individuellement (standalone) |
| `PipeTransform` / `transform()` | Interface et méthode à implémenter pour créer un pipe personnalisé (`@Pipe({ name: '...' })`) |

---

<p align="center">
  <a href="typescript.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="bdd-merise.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a>
</p>
