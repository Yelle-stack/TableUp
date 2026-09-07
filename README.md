# 🍽️ TableUp

![image_alt](https://github.com/Yelle-stack/TableUp/blob/1b868705ba6244ed08d964a092aba56bee767468/TableUpHome.png)

**TableUp** is a modern restaurant discovery and table booking web application built with React and TypeScript.

The application allows users to discover restaurants, search by cuisine, view restaurant details, read reviews, and book a table online.

TableUp also includes dedicated dashboards for **restaurant owners** and **administrators**, providing tools to manage restaurants, bookings, and approval requests.

---

## ✨ Features

### 👤 User Features

* 🏠 Modern and responsive homepage
* 🔎 Restaurant search
* 🍴 Browse restaurants by cuisine
* 📈 Trending restaurants
* 🏆 Membership section
* 📋 View detailed restaurant information
* ⭐ Read restaurant reviews
* 📅 Book a table
* ✅ Booking confirmation
* 🔐 User authentication
* 🛡️ Protected routes

### 🏪 Restaurant Owner Features

* 📊 Dedicated owner dashboard
* ➕ Create a restaurant
* 🧙 Restaurant creation wizard
* 👤 Manage restaurant profile
* 📅 Manage bookings
* ⏳ Track restaurant approval status
* ❌ Handle rejected requests

### 👨‍💼 Admin Features

* 📊 Admin dashboard
* 📈 Platform statistics
* ✅ Approve restaurant requests
* ❌ Reject restaurant requests
* 🔎 Manage restaurant approval requests

---

## 🛠️ Technologies

* **React**
* **TypeScript**
* **Vite**
* **CSS**
* **React Context API**
* **Git**
* **GitHub**

---

## 📁 Project Structure

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

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Yelle-stack/TableUp.git
```

### 2. Navigate to the project

```bash
cd TableUp
```

### 3. Install dependencies

```bash
npm install
```

### 4. Start the development server

```bash
npm run dev
```

The application will be available at the local URL provided by Vite, usually:

```text
http://localhost:5173
```

---

## 🏗️ Build for Production

To create a production build:

```bash
npm run build
```

To preview the production build locally:

```bash
npm run preview
```

---

## 🧩 Application Architecture

TableUp follows a component-based React architecture designed to keep the application modular and maintainable.

### Components

Components are organized according to their main functionality:

* `home/` — Homepage components
* `restaurant/` — Restaurant-related components
* `booking/` — Booking-related components
* `owner/` — Restaurant owner features
* `admin/` — Administration features

### Context

The `AppContext.tsx` file provides global application state and allows different components to share data and application logic.

### Pages

The `pages/` directory contains the main application views:

* Home
* Search
* Restaurant Details
* Dashboard
* Booking Confirmation
* Owner Dashboard
* Admin Dashboard

---

## 🔐 User Roles & Access

TableUp supports different types of users:

```text
                    TableUp
                       │
          ┌────────────┼────────────┐
          │            │            │
        Client       Owner        Admin
          │            │            │
       Booking      Restaurant    Platform
       & Search     Management    Management
```

Protected pages are handled through the reusable:

```text
ProtectedRoute.tsx
```

component.

---

## 📅 Booking Flow

The restaurant booking process is divided into several reusable components:

```text
Restaurant
     │
     ▼
BookingWidget
     │
     ▼
BookingForm
     │
     ▼
BookingSummary
     │
     ▼
BookingSuccess
     │
     ▼
BookingConfirmation
```

This structure makes the booking process clear and easy to maintain.

---

## 🏪 Restaurant Owner Flow

Restaurant owners can create and manage their restaurant through a dedicated workflow:

```text
Owner Dashboard
       │
       ▼
Restaurant Wizard
       │
       ▼
Approval Request
       │
       ▼
Admin Review
       │
   ┌───┴────┐
   ▼        ▼
Approved  Rejected
   │        │
   ▼        ▼
Published  Request
Restaurant Rejected
```

Restaurant requests can have different statuses:

* ⏳ Pending
* ✅ Approved
* ❌ Rejected

---

## 📊 Admin Dashboard

Administrators have access to a dedicated dashboard where they can:

* Review restaurant applications
* Approve restaurants
* Reject restaurants
* View platform statistics
* Manage approval requests

The main administrative components include:

```text
AdminDashboard.tsx
AdminApprovals.tsx
AdminStats.tsx
```

---

## 📱 Responsive Design

TableUp is designed to provide a responsive user experience across different screen sizes:

* 💻 Desktop
* 📱 Mobile
* 📟 Tablet

---

## 🔮 Future Improvements

Potential future features include:

* 💳 Online payment integration
* 📧 Email notifications
* 🔔 Booking notifications
* 🗺️ Interactive maps
* ❤️ Favorite restaurants
* 🔎 Advanced search filters
* ⭐ Enhanced review system
* 📊 More detailed owner analytics
* 🖼️ Advanced restaurant image management
* 📱 Mobile application

---

## 👩‍💻 Author

**Jelena Zeko**

Front-End Developer

GitHub: **Yelle-stack**

---

## 📄 License

This project was created as a personal portfolio project.

---

