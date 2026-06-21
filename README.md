<div align="center">
<img src="https://capsule-render.vercel.app/api?type=venom&color=0:020817,50:0c1a3a,100:0a4a6e&height=220&section=header&text=CafeMaven&fontSize=70&fontColor=e2f4f7&fontAlignY=40&desc=Cafe%20Order%20%26%20Booking%20System&descColor=7ecfde&descSize=18&descAlignY=62&animation=fadeIn" width="100%"/>
</div>

<br/>

<div align="center">

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
cafemaven/
├── backend/
│   ├── main.py               # FastAPI app entry point
│   ├── routers/
│   │   ├── auth.py           # Login & register endpoints
│   │   ├── menu.py           # Menu CRUD
│   │   ├── orders.py         # Order management
│   │   ├── reservations.py   # Table booking
│   │   └── admin.py          # Admin-only routes
│   ├── models/               # DB models
│   ├── schemas/              # Pydantic schemas
│   ├── database.py           # DB connection
│   └── auth/
│       └── jwt_handler.py    # JWT auth logic
│
└── frontend/
    ├── index.html            # Home page
    ├── login.html            # Login / Register
    ├── menu.html             # Menu page
    ├── cart.html             # Cart page
    ├── booking.html          # Table booking
    ├── admin.html            # Admin dashboard
    ├── css/
    │   └── style.css
    └── js/
        ├── main.js
        ├── cart.js
        ├── booking.js
        └── admin.js
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
git clone https://github.com/nithishkumar-dev-10/cafemaven.git
cd cafemaven
```

### 2. Setup backend

```bash
cd backend
pip install -r requirements.txt
```

### 3. Configure environment

Create a `.env` file in `/backend`:

```env
DATABASE_URL=postgresql://user:password@localhost/cafemaven
SECRET_KEY=your_jwt_secret_key
ALGORITHM=HS256
```

### 4. Run the server

```bash
uvicorn main:app --reload
```

API will be live at `http://localhost:8000`  
Swagger docs at `http://localhost:8000/docs`

### 5. Open frontend

Open any `.html` file directly in your browser or serve via Live Server (VS Code).

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

[![GitHub](https://img.shields.io/badge/◈_GitHub-0a4a6e?style=for-the-badge&logo=github&logoColor=white)](https://github.com/nithishkumar-dev-10/cafemaven)
[![LinkedIn](https://img.shields.io/badge/◈_LinkedIn-0c1a3a?style=for-the-badge&logo=linkedin&logoColor=7ecfde)](https://www.linkedin.com/in/nithish-kumar-saravanan10/)
[![Portfolio](https://img.shields.io/badge/◈_Portfolio-020817?style=for-the-badge&logoColor=7ecfde)](https://nithishkumar-dev-10.github.io/nithish-dev-portfolio/)

</div>

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a4a6e,50:0c1a3a,100:020817&height=110&section=footer&animation=fadeIn" width="100%"/>
</div>
