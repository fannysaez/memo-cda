# 🔧 GIT / GITHUB

| Commande | Définition | À quoi ça sert |
| --- | --- | --- |
| `git init` | Initialise un dépôt Git | Démarrer le suivi de version dans un dossier |
| `git clone <url>` | Copie un dépôt distant en local | Récupérer un projet existant |
| `git status` | Affiche l'état des fichiers | Voir ce qui a changé / est en attente |
| `git add <fichier>` | Ajoute au "staging area" | Préparer un fichier avant commit |
| `git commit -m "msg"` | Enregistre les changements | Créer un point de sauvegarde versionné |
| `git log` | Historique des commits | Voir qui a fait quoi, quand |
| `git diff` | Différences entre versions | Comparer avant/après modification |
| `git branch` | Liste/crée des branches | Travailler en parallèle sans casser le code principal |
| `git checkout <branche>` | Change de branche | Se déplacer entre versions du code |
| `git switch <branche>` | Équivalent moderne de checkout | Changer de branche |
| `git merge <branche>` | Fusionne une branche dans une autre | Intégrer un travail terminé |
| `git rebase` | Réécrit l'historique en réappliquant les commits | Nettoyer l'historique / éviter les merges inutiles |
| `git push` | Envoie les commits locaux vers le distant | Publier son travail |
| `git pull` | Récupère + fusionne les changements distants | Se mettre à jour |
| `git fetch` | Récupère sans fusionner | Voir les changements distants avant de les intégrer |
| `git remote -v` | Liste les dépôts distants liés | Vérifier l'URL du repo (origin) |
| `git stash` | Met de côté des modifs non commitées | Changer de contexte sans perdre son travail |
| `git reset` | Annule des commits (garde ou pas les fichiers) | Revenir en arrière localement |
| `git revert` | Annule un commit en créant un nouveau commit inverse | Annuler proprement sans réécrire l'historique |
| `.gitignore` | Fichier listant ce que Git doit ignorer | Éviter de versionner node_modules, .env, etc. |
| **HEAD** | Pointeur vers le commit courant | Repère "où on en est" |
| **Staging area (index)** | Zone tampon avant le commit | Choisir précisément quoi commiter |
| **Repository (repo)** | Dossier suivi par Git | Le projet versionné |
| **Fork** | Copie d'un repo sur son propre compte GitHub | Contribuer à un projet qu'on ne possède pas |
| **Pull Request (PR)** | Demande de fusion de code sur GitHub | Faire relire/valider avant merge |
| **Merge conflict** | Git ne sait pas choisir entre deux versions | À résoudre manuellement |
| **Clone vs Fork** | Clone = copie locale / Fork = copie sur GitHub | Deux façons de récupérer un projet |

---

[![🏠 Sommaire](https://img.shields.io/badge/🏠-Sommaire-555555?style=flat-square)](../README.md)
[![Suivant ▶](https://img.shields.io/badge/Suivant-%E2%96%B6-2E86AB?style=flat-square)](sql-postgresql.md)
