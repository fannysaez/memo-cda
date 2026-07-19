# 🧩 Programmation Orientée Objet (POO)

### Paradigme

| Terme | Définition |
| --- | --- |
| **Programme** | Suite d'instructions exécutées par un ordinateur |
| **Paradigme** | Façon de penser et d'organiser son code (procédural, orienté objet...) — pas un langage, une manière de structurer sa logique |
| **Procédural** | Le code s'exécute étape par étape, ligne par ligne (adapté aux petits projets simples) |
| **Orienté objet** | Le code est organisé en objets (données + comportements), plus facile à maintenir sur de gros projets |

### Classe, objet, interface

| Terme | Définition |
| --- | --- |
| **Classe** | Bloc de code avec des variables et des fonctions, qui sert à créer des objets — un plan/modèle, rien de concret tant qu'elle n'est pas instanciée |
| **Objet / Instance** | Entité créée à partir d'une classe, regroupant des données (attributs) et des actions (méthodes) |
| **Instancier** | Créer un objet à partir d'une classe (`new MaClasse()`) |
| **Interface** | Contrat qui liste des méthodes sans implémentation, sans état — sert au polymorphisme |
| `implements` | Fait respecter une interface par une classe ("respecte le contrat") — une classe peut implémenter plusieurs interfaces |

### Encapsulation & visibilité

| Terme | Définition |
| --- | --- |
| **Encapsulation** | Limite l'accès aux données d'un objet via des niveaux de visibilité |
| **public** | Accessible à tous, y compris depuis l'extérieur de la classe |
| **private** | Accessible seulement dans la classe qui l'a déclarée |
| **protected** | Accessible dans la classe qui l'a déclarée et ses classes filles, pas depuis l'extérieur |
| **Constructeur** | Méthode spéciale qui crée un objet et initialise ses valeurs dès sa création |
| **Getter** | Méthode qui donne un accès en lecture à une propriété privée/protégée |
| **Méthode publique** | Fait une action ou une opération sur l'objet (peut calculer, manipuler, pas juste lire) |

### Héritage & polymorphisme

| Terme | Définition |
| --- | --- |
| **Héritage** | Permet à une classe fille de réutiliser les propriétés/méthodes d'une classe mère, en ajoutant ou modifiant des fonctionnalités |
| `extends` | Fait hériter une classe d'une classe parente ("est un") — pas d'héritage multiple |
| **Classe fille / Classe mère (parent)** | Fille : hérite et peut étendre/redéfinir. Mère : fournit le comportement de base |
| **Redéfinition (override)** | Une classe fille modifie le comportement hérité d'une méthode de la classe mère |
| **Polymorphisme** | Un objet peut prendre plusieurs formes — appeler la même méthode sur des objets différents produit des comportements différents |
| **Surcharge** | Non obligatoire : sans elle, la classe fille garde le comportement hérité de la classe mère |

### Abstraction

| Terme | Définition |
| --- | --- |
| **Abstraction** | Cache les détails internes, ne montre que ce qui est nécessaire pour utiliser un objet (boîte noire) — simplifier, généraliser, s'éloigner de la réalité |
| **Classe abstraite** | Ne peut pas être instanciée ; sert de base à d'autres classes (héritage), peut mélanger méthodes concrètes et abstraites |
| **Méthode abstraite** | Déclarée sans implémentation — les classes filles doivent l'implémenter pour pouvoir être instanciées |
| **Méthode concrète** | Méthode avec une implémentation, réutilisable telle quelle par les classes filles |

### Architecture multicouche

| Terme | Définition |
| --- | --- |
| **Architecture multicouche** | Répartit les responsabilités d'une application entre plusieurs éléments, chacun avec un rôle précis |
| **Model** | Représente une entité, avec propriétés et logique métier (validation, transformation) — correspond en général à la BDD |
| **DTO** *(Data Transfer Object)* | Structure les données pour l'affichage/transmission entre couches, sans logique métier (juste du formatage) |
| **Repository / DAO** *(Data Access Object)* | Gère l'accès aux données. Un DAO déclare le contrat d'accès ; un Repository peut l'implémenter et propose une manipulation métier plus riche (pas l'inverse) |
| **Service** | Contient la logique métier de l'application |
| **Controller** | Reçoit les données d'une requête et renvoie la réponse |
| **Middleware** | Traitement intermédiaire (validation, logging, etc.) placé entre la requête et le controller |
| **Router** | Aiguille la requête vers le bon controller et renvoie la réponse au client |

---

<p align="center">
  <a href="uml.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="typescript.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a>
</p>
