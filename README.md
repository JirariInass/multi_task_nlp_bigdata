Multi-task NLP & Big Data Project

Ce projet contient un environnement complet pour le traitement NLP avec Spark et Jupyter, utilisant Docker pour la portabilité et la reproductibilité.

1️⃣ Cloner le projet
git clone https://github.com/<ton-utilisateur>/<nom-du-projet>.git
cd <nom-du-projet>


Remplace <ton-utilisateur> et <nom-du-projet> par ton nom GitHub et le nom du dépôt.

2️⃣ Prérequis

Chaque membre doit avoir installé :

Docker Desktop
 (Windows/Mac)
ou Docker Engine + Docker Compose (Linux)

Git

Vérification des installations :

docker --version
docker compose version
git --version

3️⃣ Lancer l’environnement Docker

Depuis le dossier du projet (où se trouve docker-compose.yml) :

docker compose up -d


-d = détaché (arrière-plan)

Sans -d, les logs s’affichent dans le terminal

Cela va créer et lancer tous les containers nécessaires :

Jupyter Notebook

Spark master et workers

HDFS (si configuré)

4️⃣ Accéder à Jupyter Notebook

Ouvrir le navigateur sur :

http://localhost:8888


Si un token ou mot de passe est demandé, récupérer le token avec :

docker logs <nom_du_container_jupyter>

5️⃣ Structure du projet
multi_task_nlp_bigdata/
│
├─ notebooks/               # Tous les notebooks Jupyter
├─ Dockerfile               # (Si personnalisé)
├─ docker-compose.yml       # Décrit tous les services Docker
├─ requirements.txt         # Librairies Python à installer
├─ data/                    # Datasets (si inclus)
└─ README.md                # Ce fichier

6️⃣ Ajouter/modifier du code

Faire vos changements dans notebooks/ ou dans les scripts Python.

Commit et push sur GitHub :

git add .
git commit -m "Description des changements"
git push origin main

7️⃣ Notes importantes

Les datasets volumineux ou confidentiels ne sont pas inclus dans le dépôt. Ils doivent être téléchargés séparément.

Pour reconstruire un container après modification du Dockerfile :

docker compose build
docker compose up -d
