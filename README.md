# Vite & Gourmand - Environnement Docker

## Architecture

Ce repository contient la configuration Docker permettant de lancer l’application Vite & Gourmand en local avec tous ses services :

- Frontend : application JavaScript SPA
- Backend : API Symfony
- MariaDB : données relationnelles
- MongoDB : statistiques
- Mailhog : tests d'envoi d'emails

Cet environnement permet de reproduire le projet de manière isolée et cohérente sur n’importe quelle machine.

---

## Prérequis
- Docker Desktop
- Git

---

## Lancer le projet

1. Cloner les repositories :
```bash
git clone https://github.com/Milady28002/ECF_FrontEnd.git
git clone https://github.com/Milady28002/ECF_BackEnd_API.git
git clone https://github.com/Milady28002/ECF_Docker.git
```

2. Lancer l'environnement Docker :
```bash
cd ECF_Docker
docker compose up -d --build
```

3. Initialiser la base de données :
```bash
docker compose exec backend php bin/console doctrine:migrations:migrate
```

---

## Accès à l'application

- Frontend -> http://localhost:3001
- Backend -> http://localhost:8000
- API Docs -> http://localhost:8000/api/doc
- Mailhog -> http://localhost:8026

---

### Fonctionnement

- Le code est monté via des volumes Docker
- Les dépendances PHP sont installées automatiquement lors du build
- Le dossier vendor est isolé pour éviter les conflits avec le code local
- La base de données est persistée via un volume Docker

---

### Repositories associés :

- Frontend-> https://github.com/Milady28002/ECF_FrontEnd.git
- Backend-> https://github.com/Milady28002/ECF_BackEnd_API.git

---

## 👩‍💻 Autrice

Projet réalisé par Sylvie Mendez (Milady)
Formation Graduate Développeur Web Full Stack