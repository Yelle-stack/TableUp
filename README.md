# 🍽️ TableUp

**TableUp** est une application web de réservation de restaurants permettant aux utilisateurs de découvrir des restaurants, rechercher des établissements, consulter leurs informations et effectuer une réservation en ligne.

L'application propose également des espaces dédiés aux **propriétaires de restaurants** et aux **administrateurs** afin de gérer les établissements, les réservations et les demandes d'approbation.

---

## ✨ Fonctionnalités

### 👤 Utilisateur

* 🏠 Page d'accueil moderne et responsive
* 🔎 Recherche de restaurants
* 🍴 Navigation par type de cuisine
* 📈 Restaurants tendance
* 🏆 Section membres / avantages
* 📋 Consultation des détails d'un restaurant
* ⭐ Consultation des avis
* 📅 Réservation d'une table
* ✅ Confirmation de réservation
* 🔐 Authentification utilisateur
* 🛡️ Protection des routes privées

### 🏪 Propriétaire de restaurant

* 📊 Tableau de bord propriétaire
* ➕ Création d'un restaurant
* 🧙‍♂️ Assistant de création de restaurant (`RestaurantWizard`)
* 👤 Gestion du profil du restaurant
* 📅 Gestion des réservations
* ⏳ Suivi du statut d'approbation
* ❌ Gestion des demandes rejetées

### 👨‍💼 Administrateur

* 📊 Tableau de bord administrateur
* 📈 Statistiques
* ✅ Validation des restaurants
* ❌ Rejet des demandes
* 🔎 Gestion des demandes d'approbation

---

## 🛠️ Technologies utilisées

* **React**
* **TypeScript**
* **Vite**
* **CSS**
* **React Context API**
* **Git & GitHub**

---

## 📁 Structure du projet

```text
TableUp/
│
├── src/
│   │
│   ├── assets/
│   │
│   ├── components/
│   │   ├── admin/
│   │   │   ├── AdminApprovals.tsx
│   │   │   └── AdminStats.tsx
│   │   │
│   │   ├── booking/
│   │   │   ├── BookingForm.tsx
│   │   │   ├── BookingSuccess.tsx
│   │   │   └── BookingSummary.tsx
│   │   │
│   │   ├── home/
│   │   │   ├── CuisineBrowse.tsx
│   │   │   ├── Hero.tsx
│   │   │   ├── MembershipSection.tsx
│   │   │   ├── NewletterCTA.tsx
│   │   │   └── TrendingRow.tsx
│   │   │
│   │   ├── owner/
│   │   │   ├── OwnerBooking.tsx
│   │   │   ├── OwnerProfilDetails.tsx
│   │   │   ├── PendingApproval.tsx
│   │   │   ├── RequestRejected.tsx
│   │   │   └── RestaurantWizard.tsx
│   │   │
│   │   ├── restaurant/
│   │   │   ├── RestaurantCard.tsx
│   │   │   ├── BookingWidget.tsx
│   │   │   ├── RestaurantHero.tsx
│   │   │   ├── RestaurantInfo.tsx
│   │   │   └── RestaurantReview.tsx
│   │   │
│   │   ├── AuthModal.tsx
│   │   ├── Footer.tsx
│   │   ├── Loader.tsx
│   │   ├── Navbar.tsx
│   │   └── ProtectedRoute.tsx
│   │
│   ├── context/
│   │   └── AppContext.tsx
│   │
│   ├── pages/
│   │   ├── admin/
│   │   │   └── AdminDashboard.tsx
│   │   │
│   │   ├── owner/
│   │   │   └── OwnerDashboard.tsx
│   │   │
│   │   ├── BookingConfirmation.tsx
│   │   ├── Dashboard.tsx
│   │   ├── Home.tsx
│   │   ├── RestaurantDetail.tsx
│   │   └── Search.tsx
│   │
│   ├── App.tsx
│   ├── index.css
│   └── main.tsx
│
├── public/
├── package.json
├── package-lock.json
└── README.md
```

---

## 🚀 Installation

Clone the repository :

```bash
git clone https://github.com/Yelle-stack/TableUp.git
```

Accéder au projet :

```bash
cd TableUp
```

Installer les dépendances :

```bash
npm install
```

---

## 💻 Lancer le projet en développement

Démarrer le serveur de développement :

```bash
npm run dev
```

L'application sera ensuite accessible depuis l'adresse indiquée par Vite, généralement :

```text
http://localhost:5173
```

---

## 🏗️ Build

Pour créer une version de production :

```bash
npm run build
```

Pour prévisualiser le build :

```bash
npm run preview
```

---

## 🧩 Architecture

TableUp utilise une architecture basée sur des **composants React réutilisables**.

### Components

Les composants sont organisés par fonctionnalité :

* `home/` → composants de la page d'accueil
* `restaurant/` → composants liés aux restaurants
* `booking/` → composants liés aux réservations
* `owner/` → fonctionnalités des propriétaires
* `admin/` → fonctionnalités administratives

Cette organisation permet de maintenir une structure claire et facilement évolutive.

### Context

`AppContext.tsx` centralise l'état global de l'application et permet aux différents composants d'accéder aux données partagées.

### Pages

Le dossier `pages/` contient les différentes vues principales de l'application :

* Home
* Search
* Restaurant Details
* Dashboard
* Booking Confirmation
* Owner Dashboard
* Admin Dashboard

---

## 🔐 Gestion des accès

TableUp distingue plusieurs types d'utilisateurs :

```text
Utilisateur
    │
    ├── Client
    │
    ├── Propriétaire
    │
    └── Administrateur
```

Les routes nécessitant une authentification sont protégées grâce au composant :

```text
ProtectedRoute.tsx
```

---

## 📅 Parcours de réservation

Le parcours utilisateur est organisé autour de plusieurs composants :

```text
Restaurant
     ↓
BookingWidget
     ↓
BookingForm
     ↓
BookingSummary
     ↓
BookingSuccess
     ↓
BookingConfirmation
```

L'utilisateur peut ainsi sélectionner les informations nécessaires à sa réservation puis obtenir une confirmation.

---

## 🏪 Parcours propriétaire

Un propriétaire peut créer et gérer son restaurant :

```text
Owner Dashboard
       ↓
Restaurant Wizard
       ↓
Demande d'approbation
       ↓
Admin Approval
       ↓
Restaurant publié
```

Les demandes peuvent être :

* ⏳ En attente
* ✅ Approuvées
* ❌ Rejetées

---

## 📊 Tableau de bord administrateur

L'administrateur dispose d'un espace permettant notamment de :

* consulter les demandes de restaurants ;
* approuver ou rejeter les restaurants ;
* consulter les statistiques de la plateforme.

Les composants principaux sont :

```text
AdminDashboard.tsx
AdminApprovals.tsx
AdminStats.tsx
```

---

## 📱 Responsive Design

L'interface a été pensée pour fonctionner sur différents formats d'écran :

* 💻 Desktop
* 📱 Mobile
* 📟 Tablet

---

## 🔮 Améliorations futures

Plusieurs fonctionnalités pourraient être ajoutées dans les prochaines versions :

* 💳 Paiement en ligne
* 📧 Notifications par email
* 🔔 Notifications de réservation
* 🗺️ Intégration d'une carte interactive
* ⭐ Système d'avis plus avancé
* ❤️ Restaurants favoris
* 📱 Application mobile
* 🔎 Filtres de recherche avancés
* 📊 Statistiques plus détaillées pour les propriétaires
* 🖼️ Gestion avancée des photos des restaurants

---

## 👩‍💻 Auteur

**Jelena Zeko**

Front-End Developer

GitHub : **Yelle-stack**

---

## 📄 Licence

Ce projet a été développé dans le cadre d'un projet personnel / portfolio.

