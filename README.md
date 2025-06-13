# 🚀 WordPress avec Docker Compose

Ce projet déploie un site WordPress complet avec sa base de données MySQL à l’aide de **Docker Compose**.  
Il est idéal pour les développeurs souhaitant tester ou héberger un site WordPress localement, de manière rapide et isolée.

---

## 🎯 Objectif

- Déployer une instance WordPress avec une base de données MySQL
- Utiliser des conteneurs Docker séparés pour WordPress et MySQL
- Faciliter l’installation sur n’importe quelle machine (Windows, Linux, Mac)

---

## 🧱 Structure des services

Le fichier `docker-compose.yaml` contient deux services principaux :

### 🔹 db
- Image utilisée : `mysql:5.7`
- Conteneur de base de données MySQL
- Données stockées dans un **volume Docker** (persistantes)
- Variables d’environnement pour créer la base, l’utilisateur et le mot de passe

### 🔹 wordpress
- Image utilisée : `wordpress:latest`
- Application WordPress connectée au service `db`
- Accessible depuis le navigateur via le port `8080`

---

## 🛠️ Lancer le projet

1. **Cloner ce dépôt Git** :

```bash
git clone https://github.com/kasa225/wordpress-docker.git
cd wordpress-docker

2. **Lancer les conteneurs en arrière-plan :**

docker-compose up -d
3.  **Ouvrir le navigateur et accéder à WordPress :**

http://localhost:8080

5. 📝 Variables d'environnement utilisées

Variable	Valeur définie	Description
MYSQL_ROOT_PASSWORD	exempleRoot123	Mot de passe root de MySQL
MYSQL_DATABASE	wordpressdb	Nom de la base de données
MYSQL_USER	wpuser	Nom d'utilisateur pour WordPress
MYSQL_PASSWORD	exemplePass123	Mot de passe de l'utilisateur WordPress
WORDPRESS_DB_HOST	db:3306	Adresse de la base (nom du service Docker)
WORDPRESS_DB_USER	wpuser	Identique à MYSQL_USER
WORDPRESS_DB_PASSWORD	exemplePass123	Identique à MYSQL_PASSWORD
WORDPRESS_DB_NAME	wordpressdb	Identique à MYSQL_DATABASE

6. 🧹 Arrêter et nettoyer les conteneurs

docker-compose down

