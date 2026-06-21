<div align="center">

# ☕ CafeMaven

### Cafe Order & Booking System

![Python](https://img.shields.io/badge/Python-020817?style=flat-square&logo=python&logoColor=7ecfde)
![FastAPI](https://img.shields.io/badge/FastAPI-020817?style=flat-square&logo=fastapi&logoColor=7ecfde)
![JavaScript](https://img.shields.io/badge/JavaScript-020817?style=flat-square&logo=javascript&logoColor=7ecfde)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-020817?style=flat-square&logo=postgresql&logoColor=7ecfde)
![JWT](https://img.shields.io/badge/JWT-020817?style=flat-square&logo=jsonwebtokens&logoColor=7ecfde)

*A full-stack cafe management system — browse menus, place orders, book tables, and manage everything from one dashboard.*

</div>

---

## 📌 Overview

**CafeMaven** is a full-stack web application built for cafes to streamline their operations. Customers can browse the menu, place orders, track status, and reserve tables — while admins get full control over menu management, orders, and reservations through a dedicated dashboard.

---

## ✨ Features

### 👤 Customer
- Register & login securely
- Browse menu items
- Add to cart & place orders
- Track order status in real-time
- Book tables with date & time selection
- Make payments via Razorpay / Stripe

### 🛠️ Admin
- Manage menu items (add, update, delete)
- View & manage all orders
- Handle table reservations
- Analytics dashboard

---

## 🗂️ Project Structure

```
cafe-management/
├── README.md
├── requirements.txt
│
├── backend/
│   ├── config.py
│   ├── database.py
│   ├── main.py
│   ├── dependencies.py
│   ├── menu.json
│   ├── orders.json
│   ├── reservations.json
│   ├── users.json
│   │
│   ├── models/
│   │   ├── __init__.py
│   │   ├── menu.py
│   │   ├── models_user.py
│   │   ├── order.py
│   │   └── reservation.py
│   │
│   ├── routers/
│   │   ├── __init__.py
│   │   ├── __auth_helper.py
│   │   ├── admin.py
│   │   ├── auth.py
│   │   ├── cart.py
│   │   ├── menu.py
│   │   ├── orders.py
│   │   └── reservations.py
│   │
│   ├── schemas/
│   │   ├── __init__.py
│   │   ├── menu.py
│   │   ├── order.py
│   │   ├── reservation.py
│   │   └── user.py
│   │
│   ├── services/
│   │   ├── __init__.py
│   │   ├── auth_service.py
│   │   ├── menu_service.py
│   │   ├── order_service.py
│   │   └── reservation_service.py
│   │
│   └── utils/
│       ├── __init__.py
│       └── helpers.py
│
└── frontend/
    ├── components/
    │   ├── navbar.html
    │   └── toast.html
    │
    ├── pages/
    │   ├── booking.html
    │   ├── cart.html
    │   ├── index.html
    │   ├── login.html
    │   ├── menu.html
    │   ├── orders.html
    │   └── register.html
    │
    ├── scripts/
    │   ├── api.js
    │   ├── auth.js
    │   └── utils.js
    │
    └── styles/
        ├── admin.css
        ├── auth.css
        ├── base.css
        ├── booking.css
        ├── cart.css
        ├── menu.css
        └── navbar.css
```

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | Python, FastAPI |
| **API Style** | REST API |
| **Frontend** | HTML, CSS, JavaScript |
| **Database** | PostgreSQL |
| **Auth** | JWT (JSON Web Tokens) |
| **Payment** | Razorpay / Stripe |
| **Security** | Password hashing, XSS & CSRF protection |

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- PostgreSQL
- pip

### 1. Clone the repo

```bash
git clone https://github.com/nithishkumar-dev-10/cafe-management.git
cd cafe-management
```

### 2. Setup virtual environment

```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment

Create a `.env` file inside `/backend`:

```env
DATABASE_URL=postgresql://user:password@localhost/cafemaven
SECRET_KEY=your_jwt_secret_key
ALGORITHM=HS256
```

### 5. Run the server

```bash
cd backend
uvicorn main:app --reload
```

API live at → `http://localhost:8000`  
Swagger docs → `http://localhost:8000/docs`

### 6. Open frontend

Open any file inside `frontend/pages/` in your browser or use VS Code Live Server.

---

## 🔌 API Endpoints

### Auth
| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth/register` | Register new user |
| POST | `/auth/login` | Login & get JWT token |

### Menu
| Method | Endpoint | Description |
|---|---|---|
| GET | `/menu` | Get all menu items |
| POST | `/menu` | Add menu item (admin) |
| PUT | `/menu/{id}` | Update item (admin) |
| DELETE | `/menu/{id}` | Delete item (admin) |

### Cart
| Method | Endpoint | Description |
|---|---|---|
| GET | `/cart` | Get current cart |
| POST | `/cart` | Add item to cart |
| DELETE | `/cart/{id}` | Remove item from cart |

### Orders
| Method | Endpoint | Description |
|---|---|---|
| POST | `/orders` | Place an order |
| GET | `/orders/{id}` | Track order status |
| GET | `/orders` | Get all orders (admin) |
| PUT | `/orders/{id}` | Update order status (admin) |

### Reservations
| Method | Endpoint | Description |
|---|---|---|
| POST | `/reservations` | Book a table |
| GET | `/reservations` | View all bookings (admin) |
| DELETE | `/reservations/{id}` | Cancel booking |

### Admin
| Method | Endpoint | Description |
|---|---|---|
| GET | `/admin/dashboard` | Analytics & overview |
| GET | `/admin/orders` | All orders |
| GET | `/admin/reservations` | All reservations |

---

## 🗃️ Database Schema

```
Users         → id, name, email, hashed_password, role
Menu          → id, name, description, price, category, image_url
Orders        → id, user_id, items (JSON), total, status, created_at
Reservations  → id, user_id, date, time, guests, status
```

---

## 🔐 Security

- JWT-based authentication with token expiry
- Passwords hashed using `bcrypt`
- Role-based access control (Admin vs Customer)
- XSS & CSRF protection on all form inputs

---

## 🔗 Links

<div align="center">

[![GitHub](https://img.shields.io/badge/◈_GitHub-0a4a6e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/nithishkumar-dev-10/cafe-management)
[![LinkedIn](https://img.shields.io/badge/◈_LinkedIn-0c1a3a?style=for-the-badge&logo=linkedin&logoColor=7ecfde)](https://www.linkedin.com/in/nithish-kumar-saravanan10/)
[![Portfolio](https://img.shields.io/badge/◈_Portfolio-020817?style=for-the-badge&logoColor=7ecfde)](https://nithishkumar-dev-10.github.io/nithish-dev-portfolio/)

</div>

---

<div align="center">

![Profile Views](https://komarev.com/ghpvc/?username=nithishkumar-dev-10&color=0a4a6e&style=flat-square&label=PROFILE+VIEWS)

</div>
