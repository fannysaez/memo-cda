# 🐘 PHP

### Bases

| Terme | Définition |
| --- | --- |
| `<?php ?>` | Balises délimitant le code PHP dans un fichier |
| `$variable` | Déclaration de variable (préfixée par `$`) |
| `echo` / `print` | Affiche du contenu (`echo` accepte plusieurs arguments) |
| `.` | Opérateur de concaténation de chaînes |
| `===` vs `==` | Égalité stricte (type + valeur) vs égalité "souple" (conversion de type) |
| **Type primitif** | string, int, float, bool, array, null |
| `var_dump()` | Affiche le type et la valeur d'une variable (debug) |
| `isset()` | Vérifie qu'une variable existe et n'est pas `null` |
| `empty()` | Vérifie qu'une variable est vide ou n'existe pas |

### Fonctions

| Terme | Définition |
| --- | --- |
| `function nom() {}` | Déclaration d'une fonction |
| **Paramètre** | Variable définie dans la fonction |
| **Argument** | Valeur réellement passée à l'appel |
| `return` | Renvoie une valeur et arrête la fonction |
| **Valeur par défaut** | `function f($x = 1) {}` — valeur utilisée si l'argument est omis |
| **Fonction anonyme** | `function() {}` — fonction sans nom, assignable à une variable |
| **Arrow function** | `fn($x) => $x * 2` — syntaxe courte (PHP 7.4+) |
| `use ($var)` | Importe une variable externe dans une fonction anonyme (closure) |

### Tableaux

| Terme | Définition |
| --- | --- |
| **Tableau indexé** | `[1, 2, 3]` — indices numériques automatiques |
| **Tableau associatif** | `['cle' => 'valeur']` — indices personnalisés (clé/valeur) |
| `foreach` | Boucle sur les éléments d'un tableau |
| `array_map()` | Transforme chaque élément, renvoie un nouveau tableau |
| `array_filter()` | Garde les éléments qui respectent une condition |
| `array_merge()` | Fusionne plusieurs tableaux |
| `count()` | Nombre d'éléments d'un tableau |
| `in_array()` | Vérifie qu'une valeur existe dans un tableau |

### Programmation orientée objet (POO)

| Terme | Définition |
| --- | --- |
| **Classe** | Modèle/plan décrivant les propriétés et méthodes d'un type d'objet |
| **Objet / Instance** | Élément concret créé à partir d'une classe (`new MaClasse()`) — "instancier" = créer un objet à partir d'une classe |
| `new` | Mot-clé qui crée une nouvelle instance d'une classe |
| `__construct()` | Méthode magique appelée automatiquement à l'instanciation (constructeur) |
| `$this` | Référence à l'instance courante à l'intérieur de la classe |
| **Propriété** | Variable définie dans une classe (attribut d'un objet) |
| **Méthode** | Fonction définie dans une classe |
| `public` / `private` / `protected` | Visibilité d'une propriété/méthode (accessible partout / dans la classe seulement / dans la classe et ses enfants) |
| `extends` | Fait hériter une classe d'une classe parente |
| `parent::` | Appelle une méthode ou le constructeur de la classe parente |
| **Interface** | Contrat définissant des méthodes à implémenter, sans logique |
| `implements` | Fait respecter une interface par une classe |
| `abstract` | Classe/méthode qui ne peut pas être instanciée / doit être redéfinie par les classes enfants |
| `static` | Propriété/méthode appartenant à la classe elle-même, et non à une instance (`MaClasse::methode()`) |

### Base de données (PDO)

| Terme | Définition |
| --- | --- |
| **PDO** | Extension d'accès aux bases de données (interface commune, requêtes préparées) |
| `new PDO(...)` | Crée une instance de connexion à la base de données |
| **Requête préparée** | Requête avec paramètres liés séparément, protège contre les injections SQL |
| `prepare()` / `execute()` | Prépare puis exécute une requête |
| `fetch()` / `fetchAll()` | Récupère une ligne / toutes les lignes du résultat |

---

<p align="center">
  <a href="tailwindcss.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="../README.md"><img src="https://img.shields.io/badge/-RETOUR-2E86AB?style=for-the-badge" alt="Retour"></a>
</p>
