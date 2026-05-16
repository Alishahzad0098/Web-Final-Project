# 🛍️ Maison Chic — Laravel E-Commerce Platform

<p align="center">
  <img src="https://img.shields.io/badge/Laravel-12.x-red?style=for-the-badge&logo=laravel" />
  <img src="https://img.shields.io/badge/PHP-8.2-blue?style=for-the-badge&logo=php" />
  <img src="https://img.shields.io/badge/MySQL-Database-orange?style=for-the-badge&logo=mysql" />
  <img src="https://img.shields.io/badge/Theme-Black%20%26%20White-black?style=for-the-badge" />
</p>

> **Maison Chic** is a full-featured, elegantly designed e-commerce web application built with Laravel. Featuring a sleek black-and-white aesthetic, it provides a complete shopping experience for customers and a powerful admin panel for store management.

---

## 📸 Screenshots

> *(Add your screenshots here)*

| Home Page | Single Product | Admin Panel |
|-----------|---------------|-------------|
| ![Home]() | ![Product]() | ![Admin]()  |

---

## ✨ Features

### 🛒 Customer Side
- **Home Page** with dynamic hero carousel
- **Product Listing** with search and filter functionality
- **Single Product View** with detailed description
- **Product Comparison** side-by-side feature
- **Shopping Cart** — add, update, remove items
- **Checkout** with order placement
- **User Authentication** — Register, Login, Logout
- **User Profile** editing
- **Contact Us** page with message submission
- **Order History** per user

### 🔧 Admin Panel
- **Admin Dashboard** with DataTables integration
- **Product Management** — Create, Edit, Delete, View all products
- **Order Management** — View all orders and order items
- **User Management** — View and edit users
- **Carousel Management** — Manage homepage banner slides
- **Contact Messages** — View submitted messages
- **Email Notifications** — New email/order notification system

---

## 🏗️ Project Structure

```
maison-chic/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── CarouselController.php
│   │   │   ├── CartController.php
│   │   │   ├── ContactController.php
│   │   │   ├── Controller.php
│   │   │   ├── DataTableController.php
│   │   │   ├── OrderController.php
│   │   │   ├── ProductController.php
│   │   │   └── UserController.php
│   │   └── Kernel.php
│   ├── Mail/
│   ├── Models/
│   │   ├── Admin.php
│   │   ├── Carousel.php
│   │   ├── Cart.php
│   │   ├── ContactMessage.php
│   │   ├── Order.php
│   │   ├── Orderitem.php
│   │   ├── Products.php
│   │   └── User.php
│   └── Providers/
├── database/
│   ├── factories/
│   └── migrations/
│       ├── create_users_table.php
│       ├── create_carousels_table.php
│       ├── create_admins_table.php
│       ├── create_carts_table.php
│       ├── create_orders_table.php
│       ├── create_products_table.php
│       ├── create_orderitems_table.php
│       └── ...
├── resources/
│   └── views/
│       ├── carousel/
│       ├── emails/
│       ├── layout/
│       ├── vendor/
│       ├── About.blade.php
│       ├── Cart.blade.php
│       ├── Checkout.blade.php
│       ├── Compare.blade.php
│       ├── Contact.blade.php
│       ├── Home.blade.php
│       ├── login.blade.php
│       ├── register.blade.php
│       ├── Singleproduct.blade.php
│       ├── Searchitem.blade.php
│       ├── Products.blade.php
│       ├── admintable.blade.php
│       ├── Ordertable.blade.php
│       ├── Orderitemstable.blade.php
│       ├── Productable.blade.php
│       ├── Productsform.blade.php
│       ├── Products.edit.blade.php
│       ├── useredit.blade.php
│       └── layout.blade.php
└── ...
```

---

## 🗃️ Database Schema

| Table          | Description                          |
|----------------|--------------------------------------|
| `users`        | Registered customers                 |
| `admins`       | Admin panel users                    |
| `products`     | Product catalog                      |
| `carts`        | Shopping cart items                  |
| `orders`       | Customer orders                      |
| `orderitems`   | Individual items in each order       |
| `carousels`    | Homepage banner slides               |
| `contact_messages` | Messages from the contact form  |
| `cache`        | Laravel cache table                  |
| `jobs`         | Laravel queue jobs                   |

---

## 🛠️ Tech Stack

| Layer        | Technology                        |
|--------------|-----------------------------------|
| Backend      | PHP 8.2, Laravel 12.x             |
| Frontend     | Blade Templates, HTML, CSS, JS    |
| Database     | MySQL                             |
| Local Server | XAMPP (Apache + MySQL)            |
| Styling      | Custom CSS — Black & White Theme  |
| Tables       | DataTables.js                     |
| Package Mgr  | Composer 2.x, NPM                 |

---

## ⚙️ Installation & Setup

### Prerequisites
- PHP >= 8.2
- Composer 2.x
- MySQL
- XAMPP (or any local server)
- Node.js & NPM

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/your-username/maison-chic.git
cd maison-chic

# 2. Install PHP dependencies
composer install

# 3. Install Node dependencies
npm install && npm run dev

# 4. Copy environment file
cp .env.example .env

# 5. Generate application key
php artisan key:generate

# 6. Configure your database in .env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=maison_chic
DB_USERNAME=root
DB_PASSWORD=

# 7. Run migrations
php artisan migrate

# 8. (Optional) Seed the database
php artisan db:seed

# 9. Start the development server
php artisan serve
```

Visit: **http://localhost:8000**

---

## 🔐 Default Admin Access

> *(Update these credentials after first login)*

```
URL:      /admin/login  (or as configured)
Email:    admin@example.com
Password: password
```

---

## 📧 Email Configuration

This project supports email notifications (new orders, contact messages). Configure your mail driver in `.env`:

```env
MAIL_MAILER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=your_username
MAIL_PASSWORD=your_password
MAIL_FROM_ADDRESS=noreply@maisonchic.com
MAIL_FROM_NAME="Maison Chic"
```

---

## 🚀 Deployment

```bash
# Optimize for production
php artisan config:cache
php artisan route:cache
php artisan view:cache

# Run migrations on production DB
php artisan migrate --force
```

---

## 📁 Key Pages & Routes

| Route            | View                    | Description              |
|------------------|-------------------------|--------------------------|
| `/`              | `Home.blade.php`        | Landing page             |
| `/products`      | `Productindex.blade.php`| All products             |
| `/product/{id}`  | `Singleproduct.blade.php`| Product detail          |
| `/cart`          | `Cart.blade.php`        | Shopping cart            |
| `/checkout`      | `Checkout.blade.php`    | Order checkout           |
| `/compare`       | `Compare.blade.php`     | Product comparison       |
| `/contact`       | `Contact.blade.php`     | Contact form             |
| `/register`      | `register.blade.php`    | User registration        |
| `/login`         | `login.blade.php`       | User login               |
| `/admin`         | `admintable.blade.php`  | Admin dashboard          |
| `/admin/orders`  | `Ordertable.blade.php`  | Manage orders            |
| `/admin/products`| `Productable.blade.php` | Manage products          |

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## 👨‍💻 Author

**Ali Shahzad**
- 📍 Rahim Yar Khan, Pakistan
- 🎓 BS Computer Science — KFUEIT
- 💼 [Fiverr](https://fiverr.com/) | [Upwork](https://upwork.com/) | [GitHub](https://github.com/)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

<p align="center">Made with ❤️ using Laravel | Maison Chic © 2026</p>
