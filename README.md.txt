# WordPress avec Docker Compose

## Objectif

Déployer un blog WordPress avec sa base de données MySQL via Docker Compose.

## Structure

- `db`: service MySQL avec un volume pour les données
- `wordpress`: service CMS connecté à la base

## Lancer le projet

1. Cloner le repo
2. Lancer dans un terminal :

```bash
docker-compose up -d
