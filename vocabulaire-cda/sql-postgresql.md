# 🗄️ SQL / POSTGRESQL (terminal `psql`)

### Commandes terminal `psql`

| Commande | Utilité |
| --- | --- |
| `psql -U user -d dbname` | Se connecter à une base |
| `\l` | Lister les bases de données |
| `\c dbname` | Se connecter à une base |
| `\dt` | Lister les tables |
| `\d nom_table` | Décrire une table (colonnes, types, clés) |
| `\du` | Lister les utilisateurs/rôles |
| `\q` | Quitter psql |

### Langage SQL

| Terme | Définition |
| --- | --- |
| `SELECT` | Sélectionner des données |
| `FROM` | Préciser la table source |
| `WHERE` | Filtrer les lignes |
| `INSERT INTO` | Ajouter une ligne |
| `UPDATE` | Modifier des données existantes |
| `DELETE` | Supprimer des lignes |
| `CREATE TABLE` | Créer une table |
| `ALTER TABLE` | Modifier la structure d'une table |
| `DROP TABLE` | Supprimer une table |

### Clés & contraintes

| Terme | Définition |
| --- | --- |
| **PRIMARY KEY** | Identifiant unique de chaque ligne |
| **FOREIGN KEY** | Clé qui référence la clé primaire d'une autre table (lien entre tables) |
| **UNIQUE** | Impose une valeur non dupliquée |
| **NOT NULL** | Interdit les valeurs vides |
| **DEFAULT** | Valeur automatique si rien n'est fourni |
| **CHECK** | Condition que la valeur doit respecter |
| **SERIAL** | Entier auto-incrémenté (PostgreSQL) |
| **Contrainte** | Règle imposée sur une colonne/table pour garantir l'intégrité des données |

### Relations & jointures

| Terme | Définition |
| --- | --- |
| **INNER JOIN** | Ne garde que les lignes correspondant dans les deux tables |
| **LEFT JOIN** | Garde toutes les lignes de la table de gauche + correspondances |
| **RIGHT JOIN** | Garde toutes les lignes de la table de droite + correspondances |
| **FULL JOIN** | Garde toutes les lignes des deux tables |
| **One-to-many** | Une ligne liée à plusieurs autres (ex: un client → plusieurs commandes) |
| **Many-to-many** | Plusieurs liées à plusieurs, via une table de jointure |
| **Table de jointure (pivot)** | Table intermédiaire pour gérer le many-to-many |

### Divers

| Terme | Définition |
| --- | --- |
| **GROUP BY** | Regrouper des lignes pour agréger (COUNT, SUM...) |
| **HAVING** | Filtrer après un GROUP BY |
| **ORDER BY** | Trier les résultats |
| **DISTINCT** | Supprimer les doublons |
| **Index** | Structure pour accélérer les recherches |
| **Transaction** | Ensemble d'opérations exécutées "tout ou rien" |
| **COMMIT / ROLLBACK** | Valider / annuler une transaction |
| **Schéma** | Organisation logique des tables dans une base |

---

<p align="center">
  <a href="git-github.md"><img src="https://img.shields.io/badge/-PR%C3%89C%C3%89DENT-2E86AB?style=for-the-badge" alt="Précédent"></a> &nbsp;&nbsp; <a href="javascript.md"><img src="https://img.shields.io/badge/-SUIVANT-2E86AB?style=for-the-badge" alt="Suivant"></a>
</p>
