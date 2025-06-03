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

# 🎜️ App de Réservation de Billets — Documentation API (Frontend React Native)

## 📆 Description du projet

Cette application mobile permet aux utilisateurs de consulter des voyages, effectuer des réservations, et gérer leurs paiements. Le backend est développé avec **Strapi** (headless CMS) exposant des APIs REST, tandis que le frontend est développé avec **React Native**.

---

## 🚀 Stack Technique

- **Backend :** Strapi ([http://localhost:1337]([http://localhost:1337](https://dynamic-books-c66fc8ee97.strapiapp.com/)))
- **Frontend :** React Native
- **Communication :** REST API

---

## ⚙️ Base URL de l’API

```js
const API_URL = 'https://dynamic-books-c66fc8ee97.strapiapp.com/api';
// Exemple : http://192.168.1.100:1337/api
```

> 🚨 Utilise l'adresse IP locale de ton ordinateur pour que ton téléphone puisse accéder à Strapi en local.

---

## 🔐 Authentification (plugin `users-permissions`)

### ➕ Inscription

```http
POST /api/auth/local/register
```

**Body :**

```json
{
  "username": "john",
  "email": "john@example.com",
  "password": "123456"
}
```

### 🔑 Connexion

```http
POST /api/auth/local
```

**Body :**

```json
{
  "identifier": "john@example.com",
  "password": "123456"
}
```

**Réponse :**

```json
{
  "jwt": "TOKEN",
  "user": {
    "id": 1,
    "username": "john",
    "email": "john@example.com"
  }
}
```

> Stocke le `jwt` pour les appels protégés dans `AsyncStorage` ou `SecureStore`.

---

## 📃 Collections disponibles

| Collection     | Description               |
| -------------- | ------------------------- |
| `users`        | Utilisateurs              |
| `voyages`      | Voyages disponibles       |
| `reservations` | Billets réservés          |
| `paiements`    | Paiements de réservations |

---

## 🌍 Endpoints REST par collection

### 1. 🏓 Voyages (`/voyages`)

#### 🔍 Liste des voyages

```http
GET /api/voyages
```

#### 🔍 Détails d'un voyage

```http
GET /api/voyages/:id
```

#### ➕ Créer un voyage (admin)

```http
POST /api/voyages
Headers:
Authorization: Bearer <jwt>

Body :
{
  "titre": "Paris - Lyon",
  "prix": 30,
  "date_depart": "2025-07-01T09:00:00.000Z"
}
```

---

### 2. 🗓️ Réservations (`/reservations`)

#### ➕ Créer une réservation

```http
POST /api/reservations
Headers:
Authorization: Bearer <jwt>

Body :
{
  "voyage": 1,
  "user": 2,
  "places": 2
}
```

#### 📅 Voir les réservations

```http
GET /api/reservations
```

> Pour filtrer : `?filters[user][id][$eq]=2`

---

### 3. 💳 Paiements (`/paiements`)

#### ➕ Enregistrer un paiement

```http
POST /api/paiements
Headers:
Authorization: Bearer <jwt>

Body :
{
  "reservation": 4,
  "montant": 60,
  "mode_paiement": "carte"
}
```

---

## 🔐 Exemple d'appel API sécurisé (React Native)

```js
import AsyncStorage from '@react-native-async-storage/async-storage';

const getVoyages = async () => {
  const token = await AsyncStorage.getItem('jwt');
  const res = await fetch(`${API_URL}/voyages`, {
    headers: {
      Authorization: `Bearer ${token}`,
    },
  });
  const data = await res.json();
  return data;
};
```

---

## 📈 Structure suggérée React Native

```
src/
├── api/
│   └── api.js         // appels axios centralisés
├── screens/
│   ├── LoginScreen.js
│   ├── VoyageScreen.js
│   ├── ReservationScreen.js
│   └── PaiementScreen.js
├── context/
│   └── AuthContext.js
└── components/
    └── VoyageCard.js
```

---

## 🔎 Librairies recommandées

- `axios` : pour les appels API
- `@react-native-async-storage/async-storage` : stocker le JWT
- `react-navigation` : gestion des écrans
- `formik` & `yup` : gestion des formulaires
- `react-native-dotenv` : stocker les URL de façon propre

---

## 🧪 Bonnes pratiques

- 🔁 Rafraîchir le token si expiré (401)
- 🔒 Protège les routes sensibles avec JWT
- 🛏️ Utilise Postman pour tester les routes avant le frontend
- 📡 Gère les erreurs grâce à `try/catch`

---

## ✅ Permissions à configurer dans Strapi (Settings > Roles)

- `GET /voyages`
- `GET /reservations`
- `POST /auth/local`
- `POST /auth/local/register`
- `POST /reservations`
- `POST /paiements`

---

> Ce fichier README est conçu pour documenter tous les appels backend Strapi depuis un projet React Native. Il peut être enrichi si tu ajoutes d'autres collections ou relations (ex: images, villes, transporteurs, etc.).
<sub>🤫 Psst! [Strapi is hiring](https://strapi.io/careers).</sub>
