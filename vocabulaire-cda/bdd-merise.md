# 🗃️ BDD & Méthode Merise

### Bases

| Terme | Définition |
| --- | --- |
| **SGBD** | Système de Gestion de Base de Données : logiciel qui permet de créer, stocker, interroger et gérer une base de données (ex : MariaDB, PostgreSQL, SQLite) |
| **SQL** | *Structured Query Language* — langage d'interrogation des bases relationnelles, globalement agnostique vis-à-vis du SGBD utilisé |
| **Merise** | Méthode française de conception et de modélisation de systèmes d'information, structurée en trois niveaux successifs : `MCD → MLD → MPD` |
| **Modèle Entité-Association (E-A)** | Modèle sur lequel repose le MCD : décrit la sémantique du domaine métier via des entités et des associations, indépendamment de toute contrainte technique |

### MCD, MLD, MPD

| Terme | Définition |
| --- | --- |
| **MCD** | Modèle Conceptuel de Données — décrit le besoin métier (entités, associations, cardinalités), indépendamment de toute technologie ("quoi", pas "comment") |
| **MLD** | Modèle Logique de Données — traduit le MCD en tables et clés, toujours indépendant du SGBD |
| **MPD** | Modèle Physique de Données — implémentation concrète dans un SGBD précis, avec les types réels de colonnes, contraintes et index |
| **Entité** | Objet du monde réel que l'on veut représenter (ex : `User`, `Chaussures`), porteur de propriétés dont l'une sert d'identifiant |
| **Propriété / Attribut** | Caractéristique atomique qui décrit une entité ou une association (ex : `nom`, `pointure`) — devient une colonne en MLD/MPD |
| **Occurrence** | Instance concrète d'une entité ou d'une association (ex : le client "Fanny Saez" est une occurrence de l'entité `Client`) |
| **Identifiant** | Au niveau MCD, propriété qui distingue de façon unique chaque occurrence d'une entité — devient la clé primaire en MLD/MPD |
| **Association** | Lien sémantique entre deux ou plusieurs entités (ex : `possède`, `essaie`), pouvant elle-même porter des propriétés |
| **Association porteuse de données** | Association qui porte une propriété propre au couple d'entités reliées (ex : `quantité` sur une commande) — devient obligatoirement une table en MLD |

### Cardinalités & relations

| Terme | Définition |
| --- | --- |
| **Cardinalité** | Nombre minimum et maximum de fois qu'une occurrence d'une entité participe à une association, noté `min,max` |
| `1,1` | Participation **obligatoire** et **exactement une fois** |
| `0,n` | Participation **facultative**, **plusieurs fois possible** |
| `1,n` | Participation **obligatoire**, **plusieurs fois possible** |
| `0,1` | Participation facultative, **au plus une fois** |
| **Relation un-à-un** (`1,1 — 1,1`) | Chaque occurrence de A correspond à exactement une occurrence de B, et inversement |
| **Relation un-à-plusieurs** (`1,1 — 0,n`) | Un A peut être lié à plusieurs B, mais chaque B n'est lié qu'à un seul A — clé étrangère ajoutée côté `0,n` |
| **Relation plusieurs-à-plusieurs** (`0,n — 0,n`) | Un A peut être lié à plusieurs B et inversement — nécessite une table de jointure |
| **Notation Classe (UML)** | Association représentée par un simple trait entre deux classes, avec les cardinalités aux extrémités, sans symbole intermédiaire |
| **Notation Merise** | Association représentée par une ellipse nommée d'un verbe (ex : `possède`), reliée aux deux entités par des traits portant leurs cardinalités |

### Clés & tables

| Terme | Définition |
| --- | --- |
| **Table** | Traduction en MLD d'une entité du MCD |
| **Colonne** | Traduction en MLD d'une propriété du MCD |
| **Clé primaire** (`#`) | Colonne (ou ensemble de colonnes) qui identifie de façon unique chaque ligne d'une table |
| **Clé étrangère** (`#FK_`) | Colonne d'une table qui référence la clé primaire d'une autre table, matérialisant une association |
| **Clé composée** | Clé primaire formée de plusieurs colonnes (typiquement, dans une table de jointure : les deux clés étrangères combinées) |
| **Table de jointure** *(table intermédiaire)* | Table utilisée pour traduire une association plusieurs-à-plusieurs (ou porteuse de données), contenant les clés étrangères vers les deux tables reliées |
| **Contrainte** | Règle imposée sur une colonne/table pour garantir la validité des données (`NOT NULL`, `UNIQUE`, `CHECK`...) |
| **Intégrité référentielle** | Garantie qu'une clé étrangère référence toujours une ligne existante dans la table associée (aucune référence "orpheline") |
| **Dictionnaire de données** | Document préparatoire (souvent un tableur) qui recense toutes les données du besoin métier avant de construire le MCD |

### Types de données (comparatif SGBD)

| Type générique | PostgreSQL | MySQL / MariaDB | SQLite |
| --- | --- | --- | --- |
| Entier | `INTEGER` | `INT` | `INTEGER` |
| Identifiant auto-incrémenté | `SERIAL` | `INT ... AUTO_INCREMENT` | `INTEGER PRIMARY KEY` |
| Texte court | `VARCHAR(n)` | `VARCHAR(n)` | `TEXT` |
| Texte long | `TEXT` | `TEXT` | `TEXT` |
| Nombre décimal | `NUMERIC(p,s)` | `DECIMAL(p,s)` | `REAL` |
| Booléen | `BOOLEAN` | `TINYINT(1)` (pas de vrai booléen) | `INTEGER` (0/1, pas de vrai booléen) |
| Date | `DATE` | `DATE` | `TEXT` (convention `YYYY-MM-DD`) |
| Date + heure | `TIMESTAMP` | `DATETIME` | `TEXT` (convention ISO 8601) |

> **À retenir :** SQLite a un typage dynamique (le type déclaré n'est qu'une indication) ; PostgreSQL et MySQL/MariaDB ont un typage strict.

### Relationnel vs NoSQL

| Terme | Définition |
| --- | --- |
| **Base relationnelle (SQL)** | Données rangées dans des tables à structure fixe, reliées entre elles par des clés étrangères — évite les doublons d'information |
| **NoSQL** *("Not Only SQL")* | Bases dont la structure est flexible (peut varier d'un enregistrement à l'autre), pensées pour la volumétrie et la vitesse |
| **Base Document** | Chaque enregistrement est un document, souvent au format JSON (ex : MongoDB) |
| **Base Clé-valeur** | Simple paire "clé → valeur", comme un gros dictionnaire (ex : Redis) |
| **Base Colonnes larges** | Comme des tables, mais chaque ligne peut avoir des colonnes différentes (ex : Cassandra) |
| **Base Graphe** | Données sous forme de nœuds reliés par des relations, pensée pour naviguer entre eux (ex : Neo4j) |

---

<p align="center">
  <a href="angular.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="../README.md"><img src="https://img.shields.io/badge/-RETOUR-2E86AB?style=for-the-badge" alt="Retour"></a>
</p>
