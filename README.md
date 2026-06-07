# Nomads - Travel & Adventure Booking Platform

Nomads is a modern, full-featured Travel and Adventure Booking web application built with the Laravel framework. It provides a platform for users to discover exciting travel packages, view itinerary details, and seamlessly book their next adventure, while offering administrators a robust dashboard to manage travel inventory, galleries, and customer transactions.

---

## 🚀 Features

### **1. User & Authentication Features**
- **User Registration & Login**: Built-in authentication flow for travelers.
- **Email Verification**: Enforced registration security using email verification middleware.

### **2. Travel & Destination Exploration**
- **Landing Page**: Highlights popular and featured destinations, customer reviews, and partner networks.
- **Detailed Travel Packages**: Each destination features:
  - High-quality photo galleries.
  - Quick information (Featured Event, Language, Foods, Departure Date, Duration, and Package Type).
  - Clear pricing details per person.

### **3. Seamless Booking & Checkout Flow**
- **Interactive Checkout**: Travelers can initiate booking with a single click.
- **Add / Remove Members**: Option to book for multiple participants dynamically in the same transaction.
- **Visa Configuration**: Select and add Visa requirements for participants, with automatic price updates.
- **Total Calculation**: Auto-calculated checkout summaries including transactional totals.
- **Verification & Success Page**: Confirmation state for successfully placed bookings.

### **4. Admin Dashboard (Management Portal)**
Accessible only by authorized administrators (via the `admin` middleware):
- **Dashboard Overview**: Displays statistics on total packages, transaction statuses (pending, success, cancel), and revenue.
- **Travel Package Management**: Complete CRUD operations for creating, updating, and removing travel destinations.
- **Gallery Management**: Manage travel images, uploading and binding them directly to specific travel packages.
- **Transaction Management**: Review traveler bookings, update transaction status (e.g., changing status to SUCCESS, CANCEL, or PENDING), and view order details.

---

## 🛠️ Technology Stack

- **Backend Framework**: [Laravel 8](https://laravel.com) (PHP 7.3 - 8.0+)
- **Database**: MySQL / MariaDB (utilizes Eloquent ORM & migrations)
- **Frontend Utilities**:
  - [Bootstrap 5](https://getbootstrap.com) (Responsive layout & modern UI styling)
  - [Sass](https://sass-lang.com) (Custom stylesheets)
  - [Laravel Mix / Webpack](https://laravel-mix.com) (Asset compilation)
  - Vue.js (v2) & Axios (used for minor frontend operations)

---

## 📦 Project Structure

Key directories and components:
- [web.php](file:///c:/Users/satri/Documents/Development/web-app/nomad/routes/web.php): Contains public routes, checkout routes (protected by `auth` & `verified`), and admin panel routes (protected by `admin` middleware).
- [app/Models](file:///c:/Users/satri/Documents/Development/web-app/nomad/app/Models/): Database schemas and relations for [TravelPackage](file:///c:/Users/satri/Documents/Development/web-app/nomad/app/Models/TravelPackage.php), [Gallery](file:///c:/Users/satri/Documents/Development/web-app/nomad/app/Models/Gallery.php), [Transaction](file:///c:/Users/satri/Documents/Development/web-app/nomad/app/Models/Transaction.php), and [TransactionDetail](file:///c:/Users/satri/Documents/Development/web-app/nomad/app/Models/TransactionDetail.php).
- [app/Http/Controllers/Admin](file:///c:/Users/satri/Documents/Development/web-app/nomad/app/Http/Controllers/Admin/): Contains controllers for back-office administration logic.

---

## ⚙️ Installation & Local Setup

Follow these steps to run the application locally on your machine:

### **Prerequisites**
- PHP version `>= 7.3` and `< 8.1`
- Composer
- Node.js & npm
- MySQL or MariaDB

### **Step 1: Clone the Repository**
```bash
git clone https://github.com/syahreza-satria/nomads.git
cd nomads
```

### **Step 2: Install Backend Dependencies**
```bash
composer install
```

### **Step 3: Install and Compile Frontend Assets**
```bash
npm install
npm run dev
```

### **Step 4: Configure Environment Settings**
Copy the template environment file to create your own configuration:
```bash
cp .env.example .env
```
Open the `.env` file and configure your database settings:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nomads
DB_USERNAME=root
DB_PASSWORD=your_password
```
*(Also configure your `MAIL_*` settings if you want to test email verification and registration).*

### **Step 5: Generate Application Key**
```bash
php artisan key:generate
```

### **Step 6: Run Migrations**
Prepare the database tables:
```bash
php artisan migrate
```

### **Step 7: Start Development Server**
Run the Laravel development server:
```bash
php artisan serve
```
By default, the application will be accessible at: [http://localhost:8000](http://localhost:8000)

Alternatively, you can run the preconfigured development script:
```bash
composer dev
```
*(This command uses `npx concurrently` to launch `php artisan serve`, compile front-end assets, and listen to the queue automatically).*
