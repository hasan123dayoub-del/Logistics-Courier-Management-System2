# 🚚 Logistics & Courier Management System

A backend for managing courier and logistics operations, built on **Laravel 13** with a **modular architecture** — each business domain lives in its own self-contained module.

> 🚧 **Status: work in progress** — the project foundation (modular structure, roles & permissions, Auth module) is in place; business modules are being built.

![PHP](https://img.shields.io/badge/PHP-8.3+-777BB4?logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-13-FF2D20?logo=laravel&logoColor=white)
![Modules](https://img.shields.io/badge/Architecture-Modular-0e7490)

---

## 🏗 Architecture

The application is a **modular monolith** powered by [`nwidart/laravel-modules`](https://github.com/nWidart/laravel-modules). Every module has its own controllers, routes, providers, migrations, seeders, views and tests, so domains stay isolated and easy to maintain.

```text
Modules/
└── Auth/
    ├── app/
    │   ├── Http/Controllers/
    │   └── Providers/          # module service, event & route providers
    ├── config/
    ├── database/
    │   ├── migrations/
    │   └── seeders/
    ├── resources/views/
    ├── routes/
    │   ├── api.php             # versioned under /api/v1
    │   └── web.php
    ├── tests/
    └── module.json
```

Modules are enabled or disabled in `modules_statuses.json`.

**Access control** is handled by [`spatie/laravel-permission`](https://github.com/spatie/laravel-permission) (roles & permissions tables).

---

## 🛠 Tech Stack

| Layer | Technology |
| :--- | :--- |
| Language | PHP 8.3+ |
| Framework | Laravel 13 |
| Architecture | Modular monolith (`nwidart/laravel-modules`) |
| Authorization | `spatie/laravel-permission` |
| Database | MySQL / SQLite |
| Code Style | Laravel Pint |
| Testing | PHPUnit |

---

## 🚀 Getting Started

```bash
# 1. Clone the repository
git clone https://github.com/hasan123dayoub-del/Logistics-Courier-Management-System2.git
cd Logistics-Courier-Management-System2

# 2. Install dependencies, create .env, generate the key, migrate and build assets
composer run setup

# 3. Start the development server
php artisan serve
```

Useful commands:

```bash
php artisan module:list          # list modules and their status
php artisan module:make Shipment # scaffold a new module
php artisan test                 # run the test suite
```

---

## 🗺 Roadmap

- [x] Laravel 13 project setup
- [x] Modular architecture
- [x] Roles & permissions
- [x] Auth module scaffold (`/api/v1`)
- [ ] Authentication & user management
- [ ] Shipments module
- [ ] Couriers & assignments
- [ ] Shipment tracking & status history
- [ ] Reports & dashboard
