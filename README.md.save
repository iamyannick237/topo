# 🚀 Getting started with Strapi

Strapi comes with a full featured [Command Line Interface](https://docs.strapi.io/dev-docs/cli) (CLI) which lets you scaffold and manage your project in seconds.

### `develop`

Start your Strapi application with autoReload enabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-develop)

```
npm run develop
# or
yarn develop
```

### `start`

Start your Strapi application with autoReload disabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-start)

```
npm run start
# or
yarn start
```

### `build`

Build your admin panel. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-build)

```
npm run build
# or
yarn build
```

## ⚙️ Deployment

Strapi gives you many possible deployment options for your project including [Strapi Cloud](https://cloud.strapi.io). Browse the [deployment section of the documentation](https://docs.strapi.io/dev-docs/deployment) to find the best solution for your use case.

```
yarn strapi deploy
```

## 📚 Learn more

- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://strapi.io/blog) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.

---

=== APPLICATION MOBILE AVEC STRAPI & REACT NATIVE ===

1. PRÉREQUIS
-----------------------------
- Node.js v18+
- npm ou yarn
- PostgreSQL/MySQL (pour Strapi)
- Expo CLI (pour React Native)

2. INSTALLATION
-----------------------------
# Backend (Strapi)
git clone [URL_DU_PROJET]
cd backend
npm install
cp .env.example .env
# Editer le .env avec vos identifiants DB

# Frontend (React Native)
cd ../frontend
npm install
cp .env.example .env

3. LANCEMENT
-----------------------------
# Backend
npm run develop
# Admin: http://localhost:1337/admin

# Frontend
npm start
# Scanner le QR code avec Expo Go

4. ENDPOINTS API
-----------------------------
GET    /api/articles       Liste des articles
POST   /api/auth/local     Authentification
GET    /api/products?populate=*  Produits avec médias

5. DÉPLOIEMENT
-----------------------------
# Backend (choisir une option):
- Strapi Cloud: https://cloud.strapi.io
- Heroku: git push heroku main
- Docker: docker-compose up -d

# Frontend:
expo build:android  # Pour APK
expo build:ios      # Pour iOS

6. STRUCTURE
-----------------------------
backend/
  config/    # Configuration Strapi
  src/api/   # Controllers & Modèles
frontend/
  src/screens/ # Écrans d'application
  src/services/ # Appels API

7. SUPPORT
-----------------------------
- Problèmes CORS: modifier config/middlewares.js
- Réinitialisation DB: npm run strapi content-types:clear

=== FIN DU FICHIER ===

<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>
