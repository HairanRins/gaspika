# Gaspika

Gaspika est une application mobile qui aide les foyers à réduire le gaspillage alimentaire. Les utilisateurs constituent des listes de courses hebdomadaires, suivent les aliments qu'ils possèdent déjà et reçoivent une notification avant qu'un aliment n'atteigne sa date d'expiration. L'application s'appuie sur des modèles de machine learning pour prédire la durée de conservation d'un aliment et la quantité qu'il vaut la peine d'acheter, afin que les utilisateurs n'achètent que ce dont ils ont réellement besoin. Elle est organisée en monorepo comprenant une application mobile Flutter, un backend FastAPI et les modèles ML entraînés.

## Lien de la vidéo de démonstration
[Cliquer pour voir la démo](https://res.cloudinary.com/djviemljt/video/upload/v1784983705/demo_gaspika_xtsc19.mp4)

## Fonctionnalités

### Application mobile

- [x] Écrans d'accueil (onboarding)
- [x] Inscription et connexion avec authentification JWT
- [x] Listes de courses hebdomadaires : génération, modification, suppression
- [x] Filtres sur les listes de courses
- [x] Ajout d'aliments avec photo, autocomplétion, quantité et unité
- [x] Quantité, durée de conservation et conseils de stockage suggérés par les modèles de prédiction lors de l'ajout d'un aliment
- [x] Marquer un aliment comme acheté, le modifier ou le supprimer
- [x] Détails d'un aliment avec sa durée de conservation estimée
- [x] Écran d'accueil avec les aliments disponibles de la semaine
- [x] Notifications push avec compteur de non-lus, lecture et suppression
- [x] Paramètres : informations du compte, mot de passe, préférences de notification, suppression du compte

### Backend

- [x] API REST avec documentation Swagger
- [x] Authentification JWT et hachage des mots de passe avec bcrypt
- [x] PostgreSQL avec SQLAlchemy asynchrone et migrations Alembic
- [x] Mise en cache avec Redis
- [x] Notifications planifiées : alertes d'expiration et rappels de liste en fin de semaine
- [x] Notifications push via Firebase Cloud Messaging
- [x] Envoi d'images vers ImgBB
- [x] Suppression de compte avec soft delete et purge des données personnelles
- [x] Configuration Docker Compose pour l'API, PostgreSQL et Redis
- [x] Modèles ML exposés comme endpoints de prédiction de la durée de conservation et de la quantité recommandée
- [x] Durée de conservation prédite enregistrée sur l'aliment et utilisée pour planifier sa notification d'expiration

## Stack technique

|             |                                                                                                              |
| ----------- | ------------------------------------------------------------------------------------------------------------ |
| **Mobile**  | Flutter, Provider, GoRouter, Dio, Firebase Messaging, Flutter Local Notifications       |
| **Backend** | FastAPI, Uvicorn, SQLAlchemy + Alembic, PostgreSQL, Redis, APScheduler, JWT, Bcrypt, Firebase Cloud Messaging, ImgBB |
| **IA / ML** | scikit-learn, pandas, LangChain + Groq, Chroma, Sentence Transformers                                          |
| **Infra**   | Docker Compose                                                                                                 |
