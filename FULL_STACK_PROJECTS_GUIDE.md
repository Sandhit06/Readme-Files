# The Complete Full Stack Projects Guide
### Frontend + Backend + Database — Fully Integrated, Explained in Simple Words

> This guide is written for someone who already knows backend basics (Java, Spring Boot, SQL, DSA — see [JAVA_SPRING_BOOT_BACKEND_ROADMAP.md](JAVA_SPRING_BOOT_BACKEND_ROADMAP.md) in this same folder) and now wants to become a **complete full stack developer** with real, resume-ready, interview-ready projects.
>
> Everything here is explained twice: first in **simple, plain words** (like explaining to a smart friend who is new to the topic), and then in **precise technical detail** (code, schemas, configs) so you can actually build it.
>
> You do not need to memorize this file. You need to **build** from it. Reading alone will not get you a job. Typing the code, breaking it, fixing it — that will.

---

## Table of Contents

**Part 0 — Foundations**
1. [What Does "Full Stack" Actually Mean?](#1-what-does-full-stack-actually-mean)
2. [How the Pieces Talk to Each Other](#2-how-the-pieces-talk-to-each-other)
3. [The Tech Stack We Will Use (and Why)](#3-the-tech-stack-we-will-use-and-why)
4. [How To Use This Guide](#4-how-to-use-this-guide)
5. [Environment Setup Checklist (Do This Once)](#5-environment-setup-checklist-do-this-once)

**Part 1 — Project 1: ShopSphere (Full Stack E-Commerce Platform)**
6. [Project 1 Overview](#6-project-1-overview-shopsphere)
7. [Project 1: Feature List](#7-project-1-feature-list)
8. [Project 1: System Architecture](#8-project-1-system-architecture)
9. [Project 1: Database Design](#9-project-1-database-design)
10. [Project 1: Backend — Project Structure](#10-project-1-backend--project-structure)
11. [Project 1: Backend — Entities](#11-project-1-backend--entities)
12. [Project 1: Backend — Repositories](#12-project-1-backend--repositories)
13. [Project 1: Backend — DTOs and Mappers](#13-project-1-backend--dtos-and-mappers)
14. [Project 1: Backend — Security (JWT Authentication)](#14-project-1-backend--security-jwt-authentication)
15. [Project 1: Backend — Services](#15-project-1-backend--services)
16. [Project 1: Backend — Controllers (REST API)](#16-project-1-backend--controllers-rest-api)
17. [Project 1: Backend — Exception Handling](#17-project-1-backend--exception-handling)
18. [Project 1: Backend — Payments Integration (Stripe)](#18-project-1-backend--payments-integration-stripe)
19. [Project 1: Backend — application.yml and Configuration](#19-project-1-backend--applicationyml-and-configuration)
20. [Project 1: Full REST API Reference Table](#20-project-1-full-rest-api-reference-table)
21. [Project 1: Frontend — Project Structure](#21-project-1-frontend--project-structure)
22. [Project 1: Frontend — State Management (Redux Toolkit)](#22-project-1-frontend--state-management-redux-toolkit)
23. [Project 1: Frontend — API Service Layer (Axios)](#23-project-1-frontend--api-service-layer-axios)
24. [Project 1: Frontend — Core Pages and Components](#24-project-1-frontend--core-pages-and-components)
25. [Project 1: Frontend — Routing and Protected Routes](#25-project-1-frontend--routing-and-protected-routes)
26. [Project 1: Docker and Local Run Instructions](#26-project-1-docker-and-local-run-instructions)
27. [Project 1: Testing Strategy](#27-project-1-testing-strategy)
28. [Project 1: Deployment Plan](#28-project-1-deployment-plan)
29. [Project 1: Resume Bullet Points](#29-project-1-resume-bullet-points)

**Part 2 — Project 2: TaskFlow (Full Stack Real-Time Project Management Tool — Trello/Jira Clone)**
30. [Project 2 Overview](#30-project-2-overview-taskflow)
31. [Project 2: Feature List](#31-project-2-feature-list)
32. [Project 2: System Architecture](#32-project-2-system-architecture)
33. [Project 2: Database Design](#33-project-2-database-design)
34. [Project 2: Backend — Project Structure](#34-project-2-backend--project-structure)
35. [Project 2: Backend — Entities](#35-project-2-backend--entities)
36. [Project 2: Backend — WebSocket Real-Time Layer](#36-project-2-backend--websocket-real-time-layer)
37. [Project 2: Backend — Services and Business Logic](#37-project-2-backend--services-and-business-logic)
38. [Project 2: Backend — Controllers (REST + WebSocket)](#38-project-2-backend--controllers-rest--websocket)
39. [Project 2: Backend — Redis Caching Layer](#39-project-2-backend--redis-caching-layer)
40. [Project 2: Full REST + WebSocket API Reference](#40-project-2-full-rest--websocket-api-reference)
41. [Project 2: Frontend — Drag and Drop Kanban Board](#41-project-2-frontend--drag-and-drop-kanban-board)
42. [Project 2: Frontend — Real-Time WebSocket Client](#42-project-2-frontend--real-time-websocket-client)
43. [Project 2: Frontend — Component Breakdown](#43-project-2-frontend--component-breakdown)
44. [Project 2: Docker Compose and Local Run](#44-project-2-docker-compose-and-local-run)
45. [Project 2: Testing Strategy](#45-project-2-testing-strategy)
46. [Project 2: Deployment Plan](#46-project-2-deployment-plan)
47. [Project 2: Resume Bullet Points](#47-project-2-resume-bullet-points)

**Part 3 — Project 3: QuickBite (Full Stack Food Delivery Platform with Live Order Tracking)**
48. [Project 3 Overview](#48-project-3-overview-quickbite)
49. [Project 3: Feature List](#49-project-3-feature-list)
50. [Project 3: System Architecture (Multi-Actor: Customer, Restaurant, Delivery Partner, Admin)](#50-project-3-system-architecture-multi-actor-customer-restaurant-delivery-partner-admin)
51. [Project 3: Database Design](#51-project-3-database-design)
52. [Project 3: Backend — Project Structure](#52-project-3-backend--project-structure)
53. [Project 3: Backend — Entities](#53-project-3-backend--entities)
54. [Project 3: Backend — Order State Machine](#54-project-3-backend--order-state-machine)
55. [Project 3: Backend — Live Location Tracking (WebSocket + Geo)](#55-project-3-backend--live-location-tracking-websocket--geo)
56. [Project 3: Backend — Services and Controllers](#56-project-3-backend--services-and-controllers)
57. [Project 3: Full REST + WebSocket API Reference](#57-project-3-full-rest--websocket-api-reference)
58. [Project 3: Frontend — Multi-Role UI](#58-project-3-frontend--multi-role-ui)
59. [Project 3: Frontend — Live Map Tracking Component](#59-project-3-frontend--live-map-tracking-component)
60. [Project 3: Docker Compose and Local Run](#60-project-3-docker-compose-and-local-run)
61. [Project 3: Testing Strategy](#61-project-3-testing-strategy)
62. [Project 3: Deployment Plan](#62-project-3-deployment-plan)
63. [Project 3: Resume Bullet Points](#63-project-3-resume-bullet-points)

**Part 4 — Shared Full Stack Knowledge (Applies to All 3 Projects)**
64. [Authentication and Authorization Deep Dive](#64-authentication-and-authorization-deep-dive)
65. [Database Design Principles Used Across All Projects](#65-database-design-principles-used-across-all-projects)
66. [REST API Design Standards Used](#66-rest-api-design-standards-used)
67. [Error Handling Standards](#67-error-handling-standards)
68. [Frontend Architecture Patterns](#68-frontend-architecture-patterns)
69. [CI/CD Pipeline (GitHub Actions) — Reusable Template](#69-cicd-pipeline-github-actions--reusable-template)
70. [Common Full Stack Interview Questions Based On These Projects](#70-common-full-stack-interview-questions-based-on-these-projects)
71. [How To Present These Projects On Your Resume and LinkedIn](#71-how-to-present-these-projects-on-your-resume-and-linkedin)
72. [30/60/90 Day Build Plan](#72-306090-day-build-plan)
73. [Final Checklist Before You Call a Project "Done"](#73-final-checklist-before-you-call-a-project-done)

---

# Part 0 — Foundations

## 1. What Does "Full Stack" Actually Mean?

**In simple words:**

Imagine a restaurant.

- The **frontend** is the dining area — the menu, the tables, the way food is presented to you. It's what the customer sees and touches.
- The **backend** is the kitchen — where the actual cooking (business logic) happens. The customer never sees it, but nothing works without it.
- The **database** is the pantry/fridge — where all the ingredients (data) are stored so the kitchen can use them.
- The **waiter** is the API — carrying orders from the dining area to the kitchen, and carrying food back from the kitchen to the table.

A **full stack developer** is someone who can build the dining area (frontend), run the kitchen (backend), and manage the pantry (database) — and make sure the waiter (API) moves information correctly between all of them.

**In technical words:**

A full stack application typically has these layers:

```
┌─────────────────────────────────────────────────────────┐
│  PRESENTATION LAYER (Frontend)                           │
│  React / Angular / Vue — runs in the user's browser      │
│  Talks to backend using HTTP (REST) or WebSocket          │
└───────────────────────┬───────────────────────────────────┘
                         │ JSON over HTTPS
┌───────────────────────▼───────────────────────────────────┐
│  APPLICATION LAYER (Backend)                              │
│  Spring Boot (Java) — runs on a server                    │
│  Contains: Controllers → Services → Repositories           │
│  Handles: business logic, validation, security, auth       │
└───────────────────────┬───────────────────────────────────┘
                         │ SQL / JDBC / JPA
┌───────────────────────▼───────────────────────────────────┐
│  DATA LAYER (Database)                                    │
│  PostgreSQL / MySQL / MongoDB / Redis                     │
│  Stores: users, products, orders, sessions, etc.           │
└─────────────────────────────────────────────────────────────┘
```

Each layer has one job and should not try to do another layer's job. This separation is called **separation of concerns**, and it is the single most important architecture idea in all of software engineering. If you remember only one sentence from this entire document, remember this: **each layer should only know how to do its own job, and should talk to other layers only through a clean, well-defined interface (an API).**

---

## 2. How the Pieces Talk to Each Other

**In simple words:**

Think of it like ordering food through a delivery app.

1. You (the **frontend**, i.e. the app on your phone) tap "Order Now".
2. The app sends your order to the restaurant's system (the **backend**) over the internet. This is called an **API call** — a structured message like "Customer #42 wants 2 Margherita Pizzas."
3. The backend checks the pantry (**database**) — "Do we have pizza dough and cheese in stock?"
4. The backend replies back to the app: "Order confirmed, will be ready in 20 minutes."
5. The app shows you a nice confirmation screen.

**In technical words:**

The most common communication pattern is **REST (Representational State Transfer)** over **HTTP**, exchanging **JSON** (JavaScript Object Notation) data.

Example of a real request/response pair:

**Request** (frontend → backend):
```http
POST /api/v1/orders HTTP/1.1
Host: api.shopsphere.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

{
  "items": [
    { "productId": 101, "quantity": 2 },
    { "productId": 205, "quantity": 1 }
  ],
  "shippingAddressId": 7
}
```

**Response** (backend → frontend):
```json
{
  "orderId": 5023,
  "status": "CONFIRMED",
  "totalAmount": 1499.00,
  "estimatedDelivery": "2026-08-05",
  "items": [
    { "productId": 101, "name": "Wireless Mouse", "quantity": 2, "price": 599.00 },
    { "productId": 205, "name": "USB-C Cable", "quantity": 1, "price": 301.00 }
  ]
}
```

For real-time features (chat, live tracking, notifications), REST is not enough because REST is "request-response" only — the server cannot push data to the client on its own. For that, we use **WebSockets**, which keep a connection open in both directions, like a phone call instead of exchanging letters.

```
REST (like sending letters):              WebSocket (like a phone call):
Client → Request  → Server                Client ⇄ Server (connection stays open)
Client ← Response ← Server                Either side can speak anytime
(connection closes after each exchange)   (connection stays open until closed)
```

---

## 3. The Tech Stack We Will Use (and Why)

Because you already have a Java and Spring Boot background (see your existing roadmap file in this workspace), we will use a **Java-first** stack for the backend across all 3 projects, paired with **React** for the frontend. This combination (Spring Boot + React + PostgreSQL) is one of the most in-demand full stack combinations in the current job market, especially in finance, product companies, and enterprise software — the exact type of company your existing OneTB/Datastore/DQMA background suggests you are targeting.

| Layer | Technology | Why This Choice |
|---|---|---|
| Frontend | **React 18 + Vite** | Fastest dev server, huge job market demand, easiest to learn coming from any background |
| Frontend State | **Redux Toolkit** | Industry standard for predictable state management in larger apps |
| Frontend Styling | **Tailwind CSS** | Fast to write, no context-switching to separate CSS files, widely used in modern jobs |
| Frontend HTTP Client | **Axios** | Cleaner API than native `fetch`, supports interceptors (great for auth tokens) |
| Backend Framework | **Spring Boot 3.x (Java 17/21)** | Matches your existing Java expertise, most common enterprise backend in the market |
| Backend Security | **Spring Security + JWT** | Industry standard stateless authentication approach |
| Database (relational) | **PostgreSQL 15** | Most loved open-source relational database (Stack Overflow surveys), strong JSON support too |
| Database (cache) | **Redis** | Standard for caching, session storage, and rate limiting |
| Real-time | **WebSocket (STOMP over SockJS)** | Standard Java approach for real-time features in Spring Boot |
| Containerization | **Docker + Docker Compose** | Lets you run the whole stack (frontend, backend, DB, cache) with one command |
| API Documentation | **springdoc-openapi (Swagger UI)** | Auto-generates interactive API docs from your Spring Boot code |
| Testing (backend) | **JUnit 5 + Mockito + Testcontainers** | Standard Java testing stack; Testcontainers lets you test against a real Postgres in Docker |
| Testing (frontend) | **Vitest + React Testing Library** | Standard modern React testing stack |
| CI/CD | **GitHub Actions** | Free for personal repos, easy to show in interviews as a real pipeline |
| Deployment | **Render / Railway / AWS (free-tier friendly)** | Realistic, low-cost ways to put a live demo link on your resume |

You do not have to use React. If you are more comfortable with Angular or plain JavaScript, the backend explained here works identically — only the frontend chapter changes. The important architectural ideas (REST design, JWT auth, database schema, WebSocket real-time layers) are framework-agnostic.

---

## 4. How To Use This Guide

1. **Do not copy-paste blindly.** Read each code block, understand what it does, then type it yourself. Typing builds muscle memory; copy-pasting builds nothing.
2. **Build Project 1 fully before starting Project 2.** Each project reuses concepts from the previous one but adds one new major skill:
   - Project 1 (ShopSphere) teaches you: JWT auth, relational schema design, payments, REST CRUD at scale.
   - Project 2 (TaskFlow) teaches you: WebSockets, Redis caching, drag-and-drop UI, real-time collaboration.
   - Project 3 (QuickBite) teaches you: multi-actor systems, state machines, live geo-tracking, more complex authorization (three different user roles with different apps).
3. **Push to GitHub as you go**, with meaningful commit messages (`feat: add JWT login endpoint`, not `update stuff`). Recruiters and interviewers look at commit history.
4. **Deploy at least Project 1** to a live URL. A working link is worth more than a thousand words on a resume.
5. **Be ready to explain every decision.** In interviews, you will be asked *why* you chose Postgres over MongoDB, *why* JWT over sessions, *why* you designed a table a certain way. This guide explains the "why" everywhere specifically so you can answer these confidently.

---

## 5. Environment Setup Checklist (Do This Once)

Install these tools before starting any project:

| Tool | Version | Check Command |
|---|---|---|
| Java JDK | 17 or 21 | `java -version` |
| Maven | 3.9+ | `mvn -version` |
| Node.js | 20 LTS | `node -v` |
| npm | 10+ | `npm -v` |
| PostgreSQL | 15+ | `psql --version` |
| Docker Desktop | latest | `docker --version` |
| Git | latest | `git --version` |
| IDE | IntelliJ IDEA (backend) + VS Code (frontend) | — |

**Quick Windows PowerShell setup check:**

```powershell
java -version
mvn -version
node -v
npm -v
docker --version
git --version
```

If any of these commands fail, install the missing tool before continuing. Do not try to "figure it out later" — a broken environment is the #1 reason beginners give up on side projects.

---

# Part 1 — Project 1: ShopSphere (Full Stack E-Commerce Platform)

## 6. Project 1 Overview: ShopSphere

**In simple words:**

ShopSphere is an online shop, similar in spirit to Amazon or Flipkart, but scoped down to something one person can realistically build in a few weeks. A visitor can browse products, search and filter them, add items to a cart, create an account, log in, place an order, pay for it (using a test payment gateway), and track their order status. An admin can add/edit/remove products and view all orders.

**Why this project matters for your resume:**

E-commerce is the single most recognizable full stack project type to any interviewer, because it touches almost every skill a company needs: authentication, relational data modeling, payment integration, search/filter, pagination, role-based access control, and a real checkout flow. It is the closest thing to a "prove you can build a real product" project.

**In technical words:**

ShopSphere is a two-tier client-server web application:
- **Frontend:** React SPA (Single Page Application) served separately, communicating via REST + JWT.
- **Backend:** Spring Boot monolith (a single deployable application, not microservices — see note below on why) exposing a versioned REST API (`/api/v1/...`).
- **Database:** PostgreSQL, normalized relational schema.
- **Payments:** Stripe test mode integration.

> **Why a monolith and not microservices?** A common beginner mistake is to over-engineer a portfolio project into "microservices" before understanding the fundamentals. Microservices solve organizational and scaling problems that a solo side project does not have. A **well-structured monolith** (clear packages, clear layers) demonstrates good engineering judgment far better than a poorly split set of microservices. You can mention in interviews that you deliberately chose a modular monolith and explain the tradeoffs — this is a mature answer that senior engineers respect.

---

## 7. Project 1: Feature List

### 7.1 Customer-Facing Features
- Browse products with pagination (e.g., 20 products per page)
- Search products by name/description (case-insensitive, partial match)
- Filter products by category, price range, and rating
- Sort products (price low-to-high, high-to-low, newest, best-selling)
- View a single product's detail page (images, description, stock, reviews)
- Add/remove items to/from a shopping cart (persisted per logged-in user)
- Update item quantities in the cart
- Apply a discount/coupon code at checkout
- Register a new account (email + password, with email format & password strength validation)
- Log in / log out (JWT-based session)
- Reset forgotten password (via emailed reset link/token)
- View order history and order status (`PENDING`, `CONFIRMED`, `SHIPPED`, `DELIVERED`, `CANCELLED`)
- Leave a product rating and review (only if the user has purchased that product — "verified purchase")
- Checkout flow: cart review → shipping address → payment → confirmation
- Wishlist / "save for later" list

### 7.2 Admin-Facing Features
- Admin login (role-based: `ROLE_ADMIN` vs `ROLE_CUSTOMER`)
- Create / update / delete products
- Upload product images
- Manage stock levels
- View all orders across all customers, filter by status
- Update order status manually (e.g., mark as `SHIPPED`)
- View basic sales dashboard (total revenue, orders today, top-selling products)
- Manage discount coupons (create, activate/deactivate, set expiry)

### 7.3 Cross-Cutting / Non-Functional Features
- Global exception handling with consistent error JSON shape
- Input validation on both frontend and backend (never trust the frontend alone)
- Pagination on every list endpoint (never return unbounded lists)
- Rate limiting on login endpoint (prevent brute-force attacks)
- Password hashing with BCrypt (never store plain text passwords)
- CORS configuration (only allow your frontend's origin)
- Centralized logging (SLF4J + Logback)
- API documentation via Swagger UI
- Dockerized for one-command local startup

---

## 8. Project 1: System Architecture

```
                         ┌───────────────────────────────┐
                         │      React SPA (Vite)          │
                         │  Port 5173 (dev) / Nginx (prod)│
                         └───────────────┬─────────────────┘
                                         │ HTTPS / JSON / JWT in Authorization header
                         ┌───────────────▼─────────────────┐
                         │   Spring Boot Backend            │
                         │   Port 8080                      │
                         │                                   │
                         │  Controller Layer  (REST API)      │
                         │        │                           │
                         │  Service Layer     (business logic)│
                         │        │                           │
                         │  Repository Layer  (Spring Data JPA)│
                         └───────────────┬─────────────────┘
                                         │ JDBC
                         ┌───────────────▼─────────────────┐
                         │   PostgreSQL Database             │
                         │   Port 5432                       │
                         └───────────────────────────────────┘

                         ┌───────────────────────────────┐
                         │   Stripe API (external)         │◄── Payment processing
                         └───────────────────────────────────┘
```

**Layered architecture inside the backend, explained simply:**

- **Controller layer** = the receptionist. Receives HTTP requests, checks that the request "looks right" (format-wise), and hands it to the right department. Never contains business logic.
- **Service layer** = the actual department doing the work. Contains business rules like "you cannot order more than what's in stock" or "a coupon cannot be applied twice."
- **Repository layer** = the filing clerk. Only job is to fetch and save data to/from the database. Never contains business logic.

This strict separation means: if you ever need to change *how* data is stored (e.g., switch from PostgreSQL to MySQL), you only touch the repository layer. If you need to change a business rule, you only touch the service layer. If you need to change the API shape, you only touch the controller layer (and DTOs).

---

## 9. Project 1: Database Design

**In simple words:** A database schema is like a set of labeled filing cabinets, where each cabinet (table) stores one kind of thing (users, products, orders), and drawers (rows) inside each cabinet can reference drawers in other cabinets (foreign keys) — e.g., an order "points to" the customer who placed it.

### 9.1 Entity Relationship Overview

```
users (1) ──────< (many) orders
users (1) ──────< (many) reviews
users (1) ──────< (1) carts
categories (1) ──< (many) products
products (1) ────< (many) order_items
products (1) ────< (many) reviews
products (1) ────< (many) cart_items
orders (1) ──────< (many) order_items
carts (1) ───────< (many) cart_items
orders (1) ──────< (1) payments
coupons (1) ─────< (many) orders  (nullable FK — coupon optional)
```

### 9.2 Full SQL Schema (PostgreSQL)

```sql
-- ============================================================
-- ShopSphere Database Schema
-- ============================================================

CREATE TYPE user_role AS ENUM ('CUSTOMER', 'ADMIN');
CREATE TYPE order_status AS ENUM ('PENDING', 'CONFIRMED', 'SHIPPED', 'DELIVERED', 'CANCELLED');
CREATE TYPE payment_status AS ENUM ('PENDING', 'SUCCESS', 'FAILED', 'REFUNDED');

CREATE TABLE users (
    id                BIGSERIAL PRIMARY KEY,
    full_name         VARCHAR(120)  NOT NULL,
    email             VARCHAR(180)  NOT NULL UNIQUE,
    password_hash     VARCHAR(255)  NOT NULL,
    role              user_role     NOT NULL DEFAULT 'CUSTOMER',
    phone_number      VARCHAR(20),
    is_active         BOOLEAN       NOT NULL DEFAULT TRUE,
    created_at        TIMESTAMP     NOT NULL DEFAULT now(),
    updated_at        TIMESTAMP     NOT NULL DEFAULT now()
);
CREATE INDEX idx_users_email ON users(email);

CREATE TABLE addresses (
    id                BIGSERIAL PRIMARY KEY,
    user_id           BIGINT NOT NULL REFERENCES users(id) ON DELETE CASCADE,
    label             VARCHAR(50),          -- e.g. "Home", "Office"
    address_line1     VARCHAR(200) NOT NULL,
    address_line2     VARCHAR(200),
    city              VARCHAR(100) NOT NULL,
    state             VARCHAR(100) NOT NULL,
    postal_code       VARCHAR(20)  NOT NULL,
    country           VARCHAR(100) NOT NULL DEFAULT 'India',
    is_default        BOOLEAN NOT NULL DEFAULT FALSE,
    created_at        TIMESTAMP NOT NULL DEFAULT now()
);
CREATE INDEX idx_addresses_user_id ON addresses(user_id);

CREATE TABLE categories (
    id                BIGSERIAL PRIMARY KEY,
    name              VARCHAR(100) NOT NULL UNIQUE,
    slug              VARCHAR(120) NOT NULL UNIQUE,
    parent_category_id BIGINT REFERENCES categories(id)
);

CREATE TABLE products (
    id                BIGSERIAL PRIMARY KEY,
    category_id       BIGINT NOT NULL REFERENCES categories(id),
    name              VARCHAR(200) NOT NULL,
    slug              VARCHAR(220) NOT NULL UNIQUE,
    description       TEXT,
    price             NUMERIC(10,2) NOT NULL CHECK (price >= 0),
    discount_price     NUMERIC(10,2) CHECK (discount_price >= 0),
    stock_quantity    INTEGER NOT NULL DEFAULT 0 CHECK (stock_quantity >= 0),
    brand             VARCHAR(100),
    average_rating    NUMERIC(3,2) NOT NULL DEFAULT 0,
    review_count      INTEGER NOT NULL DEFAULT 0,
    is_active         BOOLEAN NOT NULL DEFAULT TRUE,
    created_at        TIMESTAMP NOT NULL DEFAULT now(),
    updated_at        TIMESTAMP NOT NULL DEFAULT now()
);
CREATE INDEX idx_products_category_id ON products(category_id);
CREATE INDEX idx_products_name_trgm ON products USING gin (name gin_trgm_ops); -- requires pg_trgm extension, powers fast search

CREATE TABLE product_images (
    id                BIGSERIAL PRIMARY KEY,
    product_id        BIGINT NOT NULL REFERENCES products(id) ON DELETE CASCADE,
    image_url         VARCHAR(500) NOT NULL,
    is_primary        BOOLEAN NOT NULL DEFAULT FALSE,
    display_order     INTEGER NOT NULL DEFAULT 0
);
CREATE INDEX idx_product_images_product_id ON product_images(product_id);

CREATE TABLE carts (
    id                BIGSERIAL PRIMARY KEY,
    user_id           BIGINT NOT NULL UNIQUE REFERENCES users(id) ON DELETE CASCADE,
    created_at        TIMESTAMP NOT NULL DEFAULT now(),
    updated_at        TIMESTAMP NOT NULL DEFAULT now()
);

CREATE TABLE cart_items (
    id                BIGSERIAL PRIMARY KEY,
    cart_id           BIGINT NOT NULL REFERENCES carts(id) ON DELETE CASCADE,
    product_id        BIGINT NOT NULL REFERENCES products(id),
    quantity          INTEGER NOT NULL CHECK (quantity > 0),
    added_at          TIMESTAMP NOT NULL DEFAULT now(),
    UNIQUE (cart_id, product_id)
);

CREATE TABLE coupons (
    id                BIGSERIAL PRIMARY KEY,
    code              VARCHAR(40) NOT NULL UNIQUE,
    discount_percent  NUMERIC(5,2) NOT NULL CHECK (discount_percent BETWEEN 0 AND 100),
    max_discount_amount NUMERIC(10,2),
    valid_from        TIMESTAMP NOT NULL,
    valid_until       TIMESTAMP NOT NULL,
    usage_limit       INTEGER,
    times_used        INTEGER NOT NULL DEFAULT 0,
    is_active         BOOLEAN NOT NULL DEFAULT TRUE
);

CREATE TABLE orders (
    id                BIGSERIAL PRIMARY KEY,
    user_id           BIGINT NOT NULL REFERENCES users(id),
    shipping_address_id BIGINT NOT NULL REFERENCES addresses(id),
    coupon_id         BIGINT REFERENCES coupons(id),
    status            order_status NOT NULL DEFAULT 'PENDING',
    subtotal_amount   NUMERIC(10,2) NOT NULL,
    discount_amount   NUMERIC(10,2) NOT NULL DEFAULT 0,
    shipping_fee      NUMERIC(10,2) NOT NULL DEFAULT 0,
    total_amount      NUMERIC(10,2) NOT NULL,
    placed_at         TIMESTAMP NOT NULL DEFAULT now(),
    updated_at        TIMESTAMP NOT NULL DEFAULT now()
);
CREATE INDEX idx_orders_user_id ON orders(user_id);
CREATE INDEX idx_orders_status ON orders(status);

CREATE TABLE order_items (
    id                BIGSERIAL PRIMARY KEY,
    order_id          BIGINT NOT NULL REFERENCES orders(id) ON DELETE CASCADE,
    product_id        BIGINT NOT NULL REFERENCES products(id),
    product_name_snapshot VARCHAR(200) NOT NULL,  -- snapshot in case product name changes later
    unit_price_snapshot NUMERIC(10,2) NOT NULL,    -- snapshot in case price changes later
    quantity          INTEGER NOT NULL CHECK (quantity > 0)
);
CREATE INDEX idx_order_items_order_id ON order_items(order_id);

CREATE TABLE payments (
    id                BIGSERIAL PRIMARY KEY,
    order_id          BIGINT NOT NULL UNIQUE REFERENCES orders(id),
    provider          VARCHAR(30) NOT NULL DEFAULT 'STRIPE',
    provider_payment_id VARCHAR(255),
    status            payment_status NOT NULL DEFAULT 'PENDING',
    amount            NUMERIC(10,2) NOT NULL,
    paid_at           TIMESTAMP
);

CREATE TABLE reviews (
    id                BIGSERIAL PRIMARY KEY,
    product_id        BIGINT NOT NULL REFERENCES products(id) ON DELETE CASCADE,
    user_id           BIGINT NOT NULL REFERENCES users(id),
    order_item_id     BIGINT REFERENCES order_items(id),  -- proves "verified purchase"
    rating            SMALLINT NOT NULL CHECK (rating BETWEEN 1 AND 5),
    comment           TEXT,
    created_at        TIMESTAMP NOT NULL DEFAULT now(),
    UNIQUE (product_id, user_id)
);
CREATE INDEX idx_reviews_product_id ON reviews(product_id);
```

**Why these design decisions matter (interview-ready explanations):**

- **`product_name_snapshot` and `unit_price_snapshot` in `order_items`**: If a product's price changes after an order is placed, the historical order must still show the price the customer actually paid. This is called **data snapshotting** and is a very common real-world requirement that beginners miss.
- **`ENUM` types for status fields**: Restricts values at the database level (not just application level), preventing invalid data like `status = 'maybe'`.
- **Indexes on foreign keys** (`idx_orders_user_id`, etc.): Without an index, looking up "all orders for user X" requires scanning the entire table. With millions of rows this is the difference between a 2ms query and a 5-second query.
- **`UNIQUE (cart_id, product_id)`**: Prevents the same product from appearing as two separate rows in one cart — enforces "one row per product per cart" at the database level, not just in application code.
- **CHECK constraints** (`price >= 0`, `rating BETWEEN 1 AND 5`): Defense in depth — even if application code has a bug, the database itself refuses invalid data.

---

## 10. Project 1: Backend — Project Structure

```
shopsphere-backend/
├── pom.xml
├── Dockerfile
├── src/
│   ├── main/
│   │   ├── java/com/shopsphere/
│   │   │   ├── ShopSphereApplication.java
│   │   │   ├── config/
│   │   │   │   ├── SecurityConfig.java
│   │   │   │   ├── CorsConfig.java
│   │   │   │   ├── OpenApiConfig.java
│   │   │   │   └── StripeConfig.java
│   │   │   ├── security/
│   │   │   │   ├── JwtTokenProvider.java
│   │   │   │   ├── JwtAuthenticationFilter.java
│   │   │   │   ├── CustomUserDetailsService.java
│   │   │   │   └── AuthEntryPointJwt.java
│   │   │   ├── entity/
│   │   │   │   ├── User.java
│   │   │   │   ├── Address.java
│   │   │   │   ├── Category.java
│   │   │   │   ├── Product.java
│   │   │   │   ├── ProductImage.java
│   │   │   │   ├── Cart.java
│   │   │   │   ├── CartItem.java
│   │   │   │   ├── Coupon.java
│   │   │   │   ├── Order.java
│   │   │   │   ├── OrderItem.java
│   │   │   │   ├── Payment.java
│   │   │   │   └── Review.java
│   │   │   ├── repository/
│   │   │   │   ├── UserRepository.java
│   │   │   │   ├── ProductRepository.java
│   │   │   │   ├── CartRepository.java
│   │   │   │   ├── OrderRepository.java
│   │   │   │   ├── CouponRepository.java
│   │   │   │   └── ReviewRepository.java
│   │   │   ├── dto/
│   │   │   │   ├── request/
│   │   │   │   │   ├── RegisterRequest.java
│   │   │   │   │   ├── LoginRequest.java
│   │   │   │   │   ├── ProductCreateRequest.java
│   │   │   │   │   ├── AddToCartRequest.java
│   │   │   │   │   └── PlaceOrderRequest.java
│   │   │   │   └── response/
│   │   │   │       ├── AuthResponse.java
│   │   │   │       ├── ProductResponse.java
│   │   │   │       ├── CartResponse.java
│   │   │   │       ├── OrderResponse.java
│   │   │   │       └── ApiErrorResponse.java
│   │   │   ├── mapper/
│   │   │   │   ├── ProductMapper.java
│   │   │   │   └── OrderMapper.java
│   │   │   ├── service/
│   │   │   │   ├── AuthService.java
│   │   │   │   ├── ProductService.java
│   │   │   │   ├── CartService.java
│   │   │   │   ├── OrderService.java
│   │   │   │   ├── PaymentService.java
│   │   │   │   └── ReviewService.java
│   │   │   ├── controller/
│   │   │   │   ├── AuthController.java
│   │   │   │   ├── ProductController.java
│   │   │   │   ├── CartController.java
│   │   │   │   ├── OrderController.java
│   │   │   │   ├── PaymentController.java
│   │   │   │   ├── ReviewController.java
│   │   │   │   └── AdminController.java
│   │   │   └── exception/
│   │   │       ├── GlobalExceptionHandler.java
│   │   │       ├── ResourceNotFoundException.java
│   │   │       ├── InsufficientStockException.java
│   │   │       └── InvalidCouponException.java
│   │   └── resources/
│   │       ├── application.yml
│   │       ├── application-dev.yml
│   │       ├── application-prod.yml
│   │       └── db/migration/           -- Flyway migration scripts
│   │           ├── V1__init_schema.sql
│   │           └── V2__seed_categories.sql
│   └── test/
│       └── java/com/shopsphere/
│           ├── service/ProductServiceTest.java
│           ├── controller/AuthControllerTest.java
│           └── integration/OrderFlowIntegrationTest.java
```

---

## 11. Project 1: Backend — Entities

**In simple words:** An "Entity" in Spring Boot/JPA is a Java class that represents one row of a database table. JPA (Java Persistence API) automatically converts between Java objects and database rows for you, so you rarely write raw SQL yourself.

### 11.1 `User.java`

```java
package com.shopsphere.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;
import java.time.LocalDateTime;

@Entity
@Table(name = "users")
@Getter
@Setter
public class User {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "full_name", nullable = false, length = 120)
    private String fullName;

    @Column(nullable = false, unique = true, length = 180)
    private String email;

    @Column(name = "password_hash", nullable = false)
    private String passwordHash;

    @Enumerated(EnumType.STRING)
    @Column(nullable = false)
    private UserRole role = UserRole.CUSTOMER;

    @Column(name = "phone_number", length = 20)
    private String phoneNumber;

    @Column(name = "is_active", nullable = false)
    private boolean active = true;

    @Column(name = "created_at", nullable = false, updatable = false)
    private LocalDateTime createdAt = LocalDateTime.now();

    @Column(name = "updated_at", nullable = false)
    private LocalDateTime updatedAt = LocalDateTime.now();

    public enum UserRole { CUSTOMER, ADMIN }
}
```

### 11.2 `Product.java`

```java
package com.shopsphere.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;
import java.math.BigDecimal;
import java.time.LocalDateTime;
import java.util.ArrayList;
import java.util.List;

@Entity
@Table(name = "products")
@Getter
@Setter
public class Product {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "category_id", nullable = false)
    private Category category;

    @Column(nullable = false, length = 200)
    private String name;

    @Column(nullable = false, unique = true, length = 220)
    private String slug;

    @Column(columnDefinition = "TEXT")
    private String description;

    @Column(nullable = false, precision = 10, scale = 2)
    private BigDecimal price;

    @Column(name = "discount_price", precision = 10, scale = 2)
    private BigDecimal discountPrice;

    @Column(name = "stock_quantity", nullable = false)
    private Integer stockQuantity = 0;

    @Column(length = 100)
    private String brand;

    @Column(name = "average_rating", nullable = false, precision = 3, scale = 2)
    private BigDecimal averageRating = BigDecimal.ZERO;

    @Column(name = "review_count", nullable = false)
    private Integer reviewCount = 0;

    @Column(name = "is_active", nullable = false)
    private boolean active = true;

    @OneToMany(mappedBy = "product", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<ProductImage> images = new ArrayList<>();

    @Column(name = "created_at", nullable = false, updatable = false)
    private LocalDateTime createdAt = LocalDateTime.now();

    @Column(name = "updated_at", nullable = false)
    private LocalDateTime updatedAt = LocalDateTime.now();

    /** Business helper: is there enough stock for a given quantity? */
    public boolean hasStockFor(int quantity) {
        return this.stockQuantity != null && this.stockQuantity >= quantity;
    }

    public void decreaseStock(int quantity) {
        if (!hasStockFor(quantity)) {
            throw new IllegalStateException("Not enough stock for product " + this.id);
        }
        this.stockQuantity -= quantity;
    }
}
```

> **Note on business logic in entities:** Notice `hasStockFor()` and `decreaseStock()` live *inside* the entity, not the service. This is intentional — it is called the **"Rich Domain Model"** pattern, where entities protect their own invariants (rules that must always be true) rather than trusting every service to remember to check stock correctly. This is a strong, interview-worthy design choice — mention it, and be ready to contrast it with an "Anemic Domain Model" (where entities are just plain data holders and all logic lives in services — a common but weaker pattern).

### 11.3 `Cart.java` and `CartItem.java`

```java
package com.shopsphere.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;
import java.util.ArrayList;
import java.util.List;

@Entity
@Table(name = "carts")
@Getter
@Setter
public class Cart {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @OneToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "user_id", nullable = false, unique = true)
    private User user;

    @OneToMany(mappedBy = "cart", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<CartItem> items = new ArrayList<>();
}
```

```java
package com.shopsphere.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;

@Entity
@Table(name = "cart_items", uniqueConstraints = @UniqueConstraint(columnNames = {"cart_id", "product_id"}))
@Getter
@Setter
public class CartItem {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "cart_id", nullable = false)
    private Cart cart;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "product_id", nullable = false)
    private Product product;

    @Column(nullable = false)
    private Integer quantity;
}
```

### 11.4 `Order.java` and `OrderItem.java`

```java
package com.shopsphere.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;
import java.math.BigDecimal;
import java.time.LocalDateTime;
import java.util.ArrayList;
import java.util.List;

@Entity
@Table(name = "orders")
@Getter
@Setter
public class Order {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "user_id", nullable = false)
    private User user;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "shipping_address_id", nullable = false)
    private Address shippingAddress;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "coupon_id")
    private Coupon coupon;

    @Enumerated(EnumType.STRING)
    @Column(nullable = false)
    private OrderStatus status = OrderStatus.PENDING;

    @Column(name = "subtotal_amount", nullable = false, precision = 10, scale = 2)
    private BigDecimal subtotalAmount;

    @Column(name = "discount_amount", nullable = false, precision = 10, scale = 2)
    private BigDecimal discountAmount = BigDecimal.ZERO;

    @Column(name = "shipping_fee", nullable = false, precision = 10, scale = 2)
    private BigDecimal shippingFee = BigDecimal.ZERO;

    @Column(name = "total_amount", nullable = false, precision = 10, scale = 2)
    private BigDecimal totalAmount;

    @OneToMany(mappedBy = "order", cascade = CascadeType.ALL, orphanRemoval = true)
    private List<OrderItem> items = new ArrayList<>();

    @Column(name = "placed_at", nullable = false, updatable = false)
    private LocalDateTime placedAt = LocalDateTime.now();

    @Column(name = "updated_at", nullable = false)
    private LocalDateTime updatedAt = LocalDateTime.now();

    public enum OrderStatus { PENDING, CONFIRMED, SHIPPED, DELIVERED, CANCELLED }

    /** Valid state transitions — protects against illegal jumps like PENDING -> DELIVERED */
    public void transitionTo(OrderStatus newStatus) {
        boolean valid = switch (this.status) {
            case PENDING     -> newStatus == OrderStatus.CONFIRMED || newStatus == OrderStatus.CANCELLED;
            case CONFIRMED   -> newStatus == OrderStatus.SHIPPED || newStatus == OrderStatus.CANCELLED;
            case SHIPPED     -> newStatus == OrderStatus.DELIVERED;
            case DELIVERED, CANCELLED -> false; // terminal states
        };
        if (!valid) {
            throw new IllegalStateException(
                "Cannot transition order from " + this.status + " to " + newStatus);
        }
        this.status = newStatus;
        this.updatedAt = LocalDateTime.now();
    }
}
```

```java
package com.shopsphere.entity;

import jakarta.persistence.*;
import lombok.Getter;
import lombok.Setter;
import java.math.BigDecimal;

@Entity
@Table(name = "order_items")
@Getter
@Setter
public class OrderItem {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "order_id", nullable = false)
    private Order order;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "product_id", nullable = false)
    private Product product;

    @Column(name = "product_name_snapshot", nullable = false, length = 200)
    private String productNameSnapshot;

    @Column(name = "unit_price_snapshot", nullable = false, precision = 10, scale = 2)
    private BigDecimal unitPriceSnapshot;

    @Column(nullable = false)
    private Integer quantity;

    public BigDecimal getLineTotal() {
        return unitPriceSnapshot.multiply(BigDecimal.valueOf(quantity));
    }
}
```

> The `transitionTo()` state machine method is the same pattern we'll use much more heavily in **Project 3 (QuickBite)**, where orders have many more possible states (restaurant accept/reject, rider assignment, etc.). Learning it here in a simple form makes Project 3 much easier later.

---

## 12. Project 1: Backend — Repositories

**In simple words:** A repository is a Java interface that gives you database operations (find, save, delete) without writing any SQL — Spring Data JPA generates the implementation for you automatically, just from the method name.

```java
package com.shopsphere.repository;

import com.shopsphere.entity.User;
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.Optional;

public interface UserRepository extends JpaRepository<User, Long> {
    Optional<User> findByEmail(String email);
    boolean existsByEmail(String email);
}
```

```java
package com.shopsphere.repository;

import com.shopsphere.entity.Product;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;

import java.math.BigDecimal;

public interface ProductRepository extends JpaRepository<Product, Long> {

    Page<Product> findByCategoryIdAndActiveTrue(Long categoryId, Pageable pageable);

    @Query("""
        SELECT p FROM Product p
        WHERE p.active = true
        AND (:keyword IS NULL OR LOWER(p.name) LIKE LOWER(CONCAT('%', :keyword, '%')))
        AND (:categoryId IS NULL OR p.category.id = :categoryId)
        AND (:minPrice IS NULL OR p.price >= :minPrice)
        AND (:maxPrice IS NULL OR p.price <= :maxPrice)
        """)
    Page<Product> search(
        @Param("keyword") String keyword,
        @Param("categoryId") Long categoryId,
        @Param("minPrice") BigDecimal minPrice,
        @Param("maxPrice") BigDecimal maxPrice,
        Pageable pageable
    );
}
```

```java
package com.shopsphere.repository;

import com.shopsphere.entity.Order;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.data.jpa.repository.JpaRepository;

public interface OrderRepository extends JpaRepository<Order, Long> {
    Page<Order> findByUserIdOrderByPlacedAtDesc(Long userId, Pageable pageable);
    Page<Order> findByStatus(Order.OrderStatus status, Pageable pageable);
}
```

```java
package com.shopsphere.repository;

import com.shopsphere.entity.Coupon;
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.Optional;

public interface CouponRepository extends JpaRepository<Coupon, Long> {
    Optional<Coupon> findByCodeAndIsActiveTrue(String code);
}
```

> **Why `@Query` with named parameters instead of method-name-derived queries for search?** Spring Data JPA can derive a query from a method name (e.g., `findByNameContainingAndCategoryId`), but once you need **optional** filters (price range might or might not be provided), method-name derivation becomes unreadable. A `@Query` with `:param IS NULL OR ...` pattern is the standard, clean way to build "search with optional filters" in JPA without hand-rolling dynamic SQL or using the more complex `Specification` API (which is the next step up if filters grow beyond ~4-5 fields).

---

## 13. Project 1: Backend — DTOs and Mappers

**In simple words:** A DTO (Data Transfer Object) is a plain object used only to move data between the frontend and backend. We never send our JPA `Entity` classes directly over the API. This matters for two reasons: (1) security — you never want to accidentally leak a field like `passwordHash` to the frontend, and (2) flexibility — the shape of your database table and the shape of your API response are allowed to be different, and often should be.

### 13.1 Request DTOs

```java
package com.shopsphere.dto.request;

import jakarta.validation.constraints.Email;
import jakarta.validation.constraints.NotBlank;
import jakarta.validation.constraints.Pattern;
import lombok.Getter;
import lombok.Setter;

@Getter @Setter
public class RegisterRequest {

    @NotBlank(message = "Full name is required")
    private String fullName;

    @NotBlank(message = "Email is required")
    @Email(message = "Email must be valid")
    private String email;

    @NotBlank(message = "Password is required")
    @Pattern(
        regexp = "^(?=.*[A-Za-z])(?=.*\\d)(?=.*[@$!%*#?&])[A-Za-z\\d@$!%*#?&]{8,}$",
        message = "Password must be at least 8 characters and include a letter, a number, and a special character"
    )
    private String password;
}
```

```java
package com.shopsphere.dto.request;

import jakarta.validation.constraints.NotBlank;
import lombok.Getter;
import lombok.Setter;

@Getter @Setter
public class LoginRequest {
    @NotBlank
    private String email;
    @NotBlank
    private String password;
}
```

```java
package com.shopsphere.dto.request;

import jakarta.validation.constraints.Min;
import jakarta.validation.constraints.NotNull;
import lombok.Getter;
import lombok.Setter;

@Getter @Setter
public class AddToCartRequest {
    @NotNull
    private Long productId;
    @Min(1)
    private int quantity;
}
```

```java
package com.shopsphere.dto.request;

import jakarta.validation.constraints.NotNull;
import lombok.Getter;
import lombok.Setter;

@Getter @Setter
public class PlaceOrderRequest {
    @NotNull
    private Long shippingAddressId;
    private String couponCode; // optional
}
```

### 13.2 Response DTOs

```java
package com.shopsphere.dto.response;

import lombok.AllArgsConstructor;
import lombok.Getter;

@Getter @AllArgsConstructor
public class AuthResponse {
    private String token;
    private String tokenType = "Bearer";
    private Long userId;
    private String fullName;
    private String role;

    public AuthResponse(String token, Long userId, String fullName, String role) {
        this.token = token;
        this.userId = userId;
        this.fullName = fullName;
        this.role = role;
    }
}
```

```java
package com.shopsphere.dto.response;

import lombok.Builder;
import lombok.Getter;
import java.math.BigDecimal;
import java.util.List;

@Getter @Builder
public class ProductResponse {
    private Long id;
    private String name;
    private String slug;
    private String description;
    private BigDecimal price;
    private BigDecimal discountPrice;
    private Integer stockQuantity;
    private String brand;
    private BigDecimal averageRating;
    private Integer reviewCount;
    private String categoryName;
    private List<String> imageUrls;
}
```

```java
package com.shopsphere.dto.response;

import lombok.Builder;
import lombok.Getter;
import java.time.LocalDateTime;

@Getter @Builder
public class ApiErrorResponse {
    private int status;
    private String error;
    private String message;
    private String path;
    private LocalDateTime timestamp;
}
```

### 13.3 Mapper — Converting Entities to DTOs

Mappers keep controllers and services clean. You can write these by hand (as below) or use **MapStruct** to auto-generate them — for a portfolio project, hand-writing them first is better for learning, then you can mention MapStruct as a "next improvement" in interviews.

```java
package com.shopsphere.mapper;

import com.shopsphere.dto.response.ProductResponse;
import com.shopsphere.entity.Product;
import com.shopsphere.entity.ProductImage;
import org.springframework.stereotype.Component;

import java.util.List;
import java.util.stream.Collectors;

@Component
public class ProductMapper {

    public ProductResponse toResponse(Product product) {
        List<String> imageUrls = product.getImages().stream()
            .map(ProductImage::getImageUrl)
            .collect(Collectors.toList());

        return ProductResponse.builder()
            .id(product.getId())
            .name(product.getName())
            .slug(product.getSlug())
            .description(product.getDescription())
            .price(product.getPrice())
            .discountPrice(product.getDiscountPrice())
            .stockQuantity(product.getStockQuantity())
            .brand(product.getBrand())
            .averageRating(product.getAverageRating())
            .reviewCount(product.getReviewCount())
            .categoryName(product.getCategory().getName())
            .imageUrls(imageUrls)
            .build();
    }
}
```

---

## 14. Project 1: Backend — Security (JWT Authentication)

**In simple words:** JWT (JSON Web Token) is like a stamped, tamper-proof wristband you get when you enter a concert. The bouncer at the entrance (login endpoint) checks your ticket once, then gives you a wristband (token) that proves who you are. For the rest of the night, you show the wristband instead of your ticket every time you want to enter a new area (protected endpoint) — nobody re-checks your original ticket, they just verify the wristband is genuine and hasn't expired.

**In technical words:** A JWT is a signed string with 3 parts separated by dots: `header.payload.signature`. The **payload** contains claims (e.g., user email, role, expiry time). The **signature** is created using a secret key on the server, so the server can verify the token wasn't tampered with, without needing to look anything up in a database — this is what makes JWT auth "stateless."

### 14.1 `JwtTokenProvider.java`

```java
package com.shopsphere.security;

import io.jsonwebtoken.*;
import io.jsonwebtoken.security.Keys;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.security.core.Authentication;
import org.springframework.stereotype.Component;

import javax.crypto.SecretKey;
import java.util.Date;

@Component
public class JwtTokenProvider {

    @Value("${app.jwt.secret}")
    private String jwtSecret;

    @Value("${app.jwt.expiration-ms}")
    private long jwtExpirationMs;

    private SecretKey key() {
        return Keys.hmacShaKeyFor(jwtSecret.getBytes());
    }

    public String generateToken(Authentication authentication) {
        CustomUserPrincipal principal = (CustomUserPrincipal) authentication.getPrincipal();
        Date now = new Date();
        Date expiry = new Date(now.getTime() + jwtExpirationMs);

        return Jwts.builder()
            .subject(principal.getEmail())
            .claim("userId", principal.getId())
            .claim("role", principal.getRole())
            .issuedAt(now)
            .expiration(expiry)
            .signWith(key())
            .compact();
    }

    public String getEmailFromToken(String token) {
        return Jwts.parser().verifyWith(key()).build()
            .parseSignedClaims(token)
            .getPayload()
            .getSubject();
    }

    public boolean validateToken(String token) {
        try {
            Jwts.parser().verifyWith(key()).build().parseSignedClaims(token);
            return true;
        } catch (JwtException | IllegalArgumentException ex) {
            // Covers: expired token, malformed token, invalid signature, unsupported token
            return false;
        }
    }
}
```

### 14.2 `JwtAuthenticationFilter.java`

```java
package com.shopsphere.security;

import jakarta.servlet.FilterChain;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.security.core.userdetails.UserDetails;
import org.springframework.security.web.authentication.WebAuthenticationDetailsSource;
import org.springframework.security.web.authentication.web.util.matcher.OrRequestMatcher;
import org.springframework.web.filter.OncePerRequestFilter;

import java.io.IOException;

public class JwtAuthenticationFilter extends OncePerRequestFilter {

    private final JwtTokenProvider tokenProvider;
    private final CustomUserDetailsService userDetailsService;

    public JwtAuthenticationFilter(JwtTokenProvider tokenProvider, CustomUserDetailsService userDetailsService) {
        this.tokenProvider = tokenProvider;
        this.userDetailsService = userDetailsService;
    }

    @Override
    protected void doFilterInternal(HttpServletRequest request, HttpServletResponse response, FilterChain chain)
            throws ServletException, IOException {
        try {
            String token = resolveToken(request);
            if (token != null && tokenProvider.validateToken(token)) {
                String email = tokenProvider.getEmailFromToken(token);
                UserDetails userDetails = userDetailsService.loadUserByUsername(email);

                var authentication = new UsernamePasswordAuthenticationToken(
                    userDetails, null, userDetails.getAuthorities());
                authentication.setDetails(new WebAuthenticationDetailsSource().buildDetails(request));
                SecurityContextHolder.getContext().setAuthentication(authentication);
            }
        } catch (Exception ex) {
            // Never throw from a filter — just leave the context unauthenticated
            SecurityContextHolder.clearContext();
        }
        chain.doFilter(request, response);
    }

    private String resolveToken(HttpServletRequest request) {
        String bearerToken = request.getHeader("Authorization");
        if (bearerToken != null && bearerToken.startsWith("Bearer ")) {
            return bearerToken.substring(7);
        }
        return null;
    }
}
```

### 14.3 `SecurityConfig.java`

```java
package com.shopsphere.config;

import com.shopsphere.security.*;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.authentication.AuthenticationManager;
import org.springframework.security.authentication.dao.DaoAuthenticationProvider;
import org.springframework.security.config.annotation.authentication.configuration.AuthenticationConfiguration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.EnableWebSecurity;
import org.springframework.security.config.http.SessionCreationPolicy;
import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.security.web.SecurityFilterChain;
import org.springframework.security.web.authentication.UsernamePasswordAuthenticationFilter;

@Configuration
@EnableWebSecurity
public class SecurityConfig {

    private final CustomUserDetailsService userDetailsService;
    private final JwtTokenProvider tokenProvider;
    private final AuthEntryPointJwt unauthorizedHandler;

    public SecurityConfig(CustomUserDetailsService userDetailsService, JwtTokenProvider tokenProvider,
                           AuthEntryPointJwt unauthorizedHandler) {
        this.userDetailsService = userDetailsService;
        this.tokenProvider = tokenProvider;
        this.unauthorizedHandler = unauthorizedHandler;
    }

    @Bean
    public PasswordEncoder passwordEncoder() {
        return new BCryptPasswordEncoder(12); // strength factor 12 — good balance of security vs speed in 2026
    }

    @Bean
    public DaoAuthenticationProvider authenticationProvider() {
        DaoAuthenticationProvider provider = new DaoAuthenticationProvider();
        provider.setUserDetailsService(userDetailsService);
        provider.setPasswordEncoder(passwordEncoder());
        return provider;
    }

    @Bean
    public AuthenticationManager authenticationManager(AuthenticationConfiguration config) throws Exception {
        return config.getAuthenticationManager();
    }

    @Bean
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {
        JwtAuthenticationFilter jwtFilter = new JwtAuthenticationFilter(tokenProvider, userDetailsService);

        http
            .csrf(csrf -> csrf.disable()) // safe to disable: we use stateless JWT, not cookies
            .exceptionHandling(ex -> ex.authenticationEntryPoint(unauthorizedHandler))
            .sessionManagement(sm -> sm.sessionCreationPolicy(SessionCreationPolicy.STATELESS))
            .authorizeHttpRequests(auth -> auth
                .requestMatchers("/api/v1/auth/**").permitAll()
                .requestMatchers("/api/v1/products/**").permitAll()
                .requestMatchers("/swagger-ui/**", "/v3/api-docs/**").permitAll()
                .requestMatchers("/api/v1/admin/**").hasRole("ADMIN")
                .anyRequest().authenticated()
            )
            .authenticationProvider(authenticationProvider())
            .addFilterBefore(jwtFilter, UsernamePasswordAuthenticationFilter.class);

        return http.build();
    }
}
```

> **Why BCrypt and not plain SHA-256 for passwords?** SHA-256 is fast — which is exactly the wrong property for password hashing, because it makes brute-force attacks cheap. BCrypt is deliberately slow and includes a "work factor" (here, 12) that you can increase over time as hardware gets faster, and it automatically salts each password so two identical passwords never produce the same hash. Never hand-roll password hashing.

> **Why `STATELESS` session policy?** It tells Spring Security not to create an `HttpSession` on the server. Combined with JWT, this means the server holds zero session state — any of your backend instances (if you ever scaled to multiple servers) can validate any token without needing shared session storage. This is essential for horizontal scalability.

### 14.4 `CustomUserDetailsService.java`

```java
package com.shopsphere.security;

import com.shopsphere.entity.User;
import com.shopsphere.repository.UserRepository;
import org.springframework.security.core.userdetails.UserDetails;
import org.springframework.security.core.userdetails.UserDetailsService;
import org.springframework.security.core.userdetails.UsernameNotFoundException;
import org.springframework.stereotype.Service;

@Service
public class CustomUserDetailsService implements UserDetailsService {

    private final UserRepository userRepository;

    public CustomUserDetailsService(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    @Override
    public UserDetails loadUserByUsername(String email) {
        User user = userRepository.findByEmail(email)
            .orElseThrow(() -> new UsernameNotFoundException("No user found with email: " + email));
        return CustomUserPrincipal.from(user);
    }
}
```

### 14.5 `AuthEntryPointJwt.java` (handles unauthenticated access attempts)

```java
package com.shopsphere.security;

import com.fasterxml.jackson.databind.ObjectMapper;
import com.shopsphere.dto.response.ApiErrorResponse;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.springframework.security.core.AuthenticationException;
import org.springframework.security.web.AuthenticationEntryPoint;
import org.springframework.stereotype.Component;

import java.time.LocalDateTime;

@Component
public class AuthEntryPointJwt implements AuthenticationEntryPoint {

    private final ObjectMapper objectMapper = new ObjectMapper().findAndRegisterModules();

    @Override
    public void commence(HttpServletRequest request, HttpServletResponse response, AuthenticationException authException)
            throws java.io.IOException {
        response.setContentType("application/json");
        response.setStatus(HttpServletResponse.SC_UNAUTHORIZED);

        ApiErrorResponse errorResponse = ApiErrorResponse.builder()
            .status(HttpServletResponse.SC_UNAUTHORIZED)
            .error("Unauthorized")
            .message("Authentication required to access this resource")
            .path(request.getRequestURI())
            .timestamp(LocalDateTime.now())
            .build();

        response.getWriter().write(objectMapper.writeValueAsString(errorResponse));
    }
}
```

---

## 15. Project 1: Backend — Services

**In simple words:** The service layer is where the "rules of the business" live — things like "you cannot check out an empty cart" or "a coupon cannot be used past its expiry date." Controllers should stay thin and simply delegate to services.

### 15.1 `AuthService.java`

```java
package com.shopsphere.service;

import com.shopsphere.dto.request.LoginRequest;
import com.shopsphere.dto.request.RegisterRequest;
import com.shopsphere.dto.response.AuthResponse;
import com.shopsphere.entity.Cart;
import com.shopsphere.entity.User;
import com.shopsphere.exception.DuplicateEmailException;
import com.shopsphere.repository.CartRepository;
import com.shopsphere.repository.UserRepository;
import com.shopsphere.security.JwtTokenProvider;
import org.springframework.security.authentication.AuthenticationManager;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.Authentication;
import org.springframework.security.crypto.password.PasswordEncoder;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

@Service
public class AuthService {

    private final UserRepository userRepository;
    private final CartRepository cartRepository;
    private final PasswordEncoder passwordEncoder;
    private final AuthenticationManager authenticationManager;
    private final JwtTokenProvider tokenProvider;

    public AuthService(UserRepository userRepository, CartRepository cartRepository,
                        PasswordEncoder passwordEncoder, AuthenticationManager authenticationManager,
                        JwtTokenProvider tokenProvider) {
        this.userRepository = userRepository;
        this.cartRepository = cartRepository;
        this.passwordEncoder = passwordEncoder;
        this.authenticationManager = authenticationManager;
        this.tokenProvider = tokenProvider;
    }

    @Transactional
    public AuthResponse register(RegisterRequest request) {
        if (userRepository.existsByEmail(request.getEmail())) {
            throw new DuplicateEmailException("An account with this email already exists");
        }

        User user = new User();
        user.setFullName(request.getFullName());
        user.setEmail(request.getEmail().toLowerCase().trim());
        user.setPasswordHash(passwordEncoder.encode(request.getPassword()));
        user.setRole(User.UserRole.CUSTOMER);
        userRepository.save(user);

        // Every new customer automatically gets an empty cart created
        Cart cart = new Cart();
        cart.setUser(user);
        cartRepository.save(cart);

        Authentication authentication = authenticate(user.getEmail(), request.getPassword());
        String token = tokenProvider.generateToken(authentication);
        return new AuthResponse(token, user.getId(), user.getFullName(), user.getRole().name());
    }

    public AuthResponse login(LoginRequest request) {
        Authentication authentication = authenticate(request.getEmail(), request.getPassword());
        User user = userRepository.findByEmail(request.getEmail())
            .orElseThrow(() -> new IllegalStateException("User should exist after successful authentication"));
        String token = tokenProvider.generateToken(authentication);
        return new AuthResponse(token, user.getId(), user.getFullName(), user.getRole().name());
    }

    private Authentication authenticate(String email, String rawPassword) {
        Authentication authentication = authenticationManager.authenticate(
            new UsernamePasswordAuthenticationToken(email, rawPassword));
        org.springframework.security.core.context.SecurityContextHolder.getContext()
            .setAuthentication(authentication);
        return authentication;
    }
}
```

### 15.2 `CartService.java`

```java
package com.shopsphere.service;

import com.shopsphere.dto.request.AddToCartRequest;
import com.shopsphere.entity.Cart;
import com.shopsphere.entity.CartItem;
import com.shopsphere.entity.Product;
import com.shopsphere.exception.InsufficientStockException;
import com.shopsphere.exception.ResourceNotFoundException;
import com.shopsphere.repository.CartRepository;
import com.shopsphere.repository.ProductRepository;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

@Service
public class CartService {

    private final CartRepository cartRepository;
    private final ProductRepository productRepository;

    public CartService(CartRepository cartRepository, ProductRepository productRepository) {
        this.cartRepository = cartRepository;
        this.productRepository = productRepository;
    }

    @Transactional
    public Cart addItem(Long userId, AddToCartRequest request) {
        Cart cart = cartRepository.findByUserId(userId)
            .orElseThrow(() -> new ResourceNotFoundException("Cart not found for user " + userId));

        Product product = productRepository.findById(request.getProductId())
            .orElseThrow(() -> new ResourceNotFoundException("Product not found: " + request.getProductId()));

        if (!product.hasStockFor(request.getQuantity())) {
            throw new InsufficientStockException(
                "Only " + product.getStockQuantity() + " left in stock for " + product.getName());
        }

        CartItem existingItem = cart.getItems().stream()
            .filter(item -> item.getProduct().getId().equals(product.getId()))
            .findFirst()
            .orElse(null);

        if (existingItem != null) {
            existingItem.setQuantity(existingItem.getQuantity() + request.getQuantity());
        } else {
            CartItem newItem = new CartItem();
            newItem.setCart(cart);
            newItem.setProduct(product);
            newItem.setQuantity(request.getQuantity());
            cart.getItems().add(newItem);
        }

        return cartRepository.save(cart);
    }

    @Transactional
    public Cart removeItem(Long userId, Long productId) {
        Cart cart = cartRepository.findByUserId(userId)
            .orElseThrow(() -> new ResourceNotFoundException("Cart not found for user " + userId));
        cart.getItems().removeIf(item -> item.getProduct().getId().equals(productId));
        return cartRepository.save(cart);
    }

    @Transactional(readOnly = true)
    public Cart getCart(Long userId) {
        return cartRepository.findByUserId(userId)
            .orElseThrow(() -> new ResourceNotFoundException("Cart not found for user " + userId));
    }
}
```

### 15.3 `OrderService.java` — The Most Important Service in This Project

**In simple words:** This is the "checkout counter." It takes everything in your cart, double-checks stock is still available (someone else might have bought the last item seconds ago), applies any coupon, calculates the final price, creates the order record, empties the cart, and hands off to payment. This is the single most business-critical piece of code in an e-commerce system, which is exactly why interviewers love asking about it.

```java
package com.shopsphere.service;

import com.shopsphere.dto.request.PlaceOrderRequest;
import com.shopsphere.entity.*;
import com.shopsphere.exception.InsufficientStockException;
import com.shopsphere.exception.InvalidCouponException;
import com.shopsphere.exception.ResourceNotFoundException;
import com.shopsphere.repository.*;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.math.BigDecimal;
import java.math.RoundingMode;
import java.time.LocalDateTime;

@Service
public class OrderService {

    private final CartRepository cartRepository;
    private final OrderRepository orderRepository;
    private final CouponRepository couponRepository;
    private final AddressRepository addressRepository;
    private final ProductRepository productRepository;

    private static final BigDecimal FLAT_SHIPPING_FEE = new BigDecimal("49.00");
    private static final BigDecimal FREE_SHIPPING_THRESHOLD = new BigDecimal("999.00");

    public OrderService(CartRepository cartRepository, OrderRepository orderRepository,
                         CouponRepository couponRepository, AddressRepository addressRepository,
                         ProductRepository productRepository) {
        this.cartRepository = cartRepository;
        this.orderRepository = orderRepository;
        this.couponRepository = couponRepository;
        this.addressRepository = addressRepository;
        this.productRepository = productRepository;
    }

    /**
     * Places an order from the user's current cart.
     * This method is wrapped in a single database transaction: if ANY step fails
     * (e.g., stock runs out midway), ALL changes are rolled back — the order is
     * never left in a half-created state. This is the core guarantee of ACID
     * transactions and is critical for anything involving money.
     */
    @Transactional
    public Order placeOrder(Long userId, PlaceOrderRequest request) {
        Cart cart = cartRepository.findByUserId(userId)
            .orElseThrow(() -> new ResourceNotFoundException("Cart not found"));

        if (cart.getItems().isEmpty()) {
            throw new IllegalStateException("Cannot place an order with an empty cart");
        }

        Address shippingAddress = addressRepository.findById(request.getShippingAddressId())
            .orElseThrow(() -> new ResourceNotFoundException("Shipping address not found"));

        Order order = new Order();
        order.setUser(cart.getUser());
        order.setShippingAddress(shippingAddress);

        BigDecimal subtotal = BigDecimal.ZERO;

        // Step 1: Re-validate stock for every item (prevents "stale cart" race conditions)
        for (CartItem cartItem : cart.getItems()) {
            Product product = productRepository.findById(cartItem.getProduct().getId())
                .orElseThrow(() -> new ResourceNotFoundException("Product no longer exists"));

            if (!product.hasStockFor(cartItem.getQuantity())) {
                throw new InsufficientStockException(
                    "Not enough stock for " + product.getName() + ". Please update your cart.");
            }

            OrderItem orderItem = new OrderItem();
            orderItem.setOrder(order);
            orderItem.setProduct(product);
            orderItem.setProductNameSnapshot(product.getName());
            orderItem.setUnitPriceSnapshot(
                product.getDiscountPrice() != null ? product.getDiscountPrice() : product.getPrice());
            orderItem.setQuantity(cartItem.getQuantity());

            order.getItems().add(orderItem);
            subtotal = subtotal.add(orderItem.getLineTotal());

            // Step 2: Deduct stock immediately (within the same transaction)
            product.decreaseStock(cartItem.getQuantity());
            productRepository.save(product);
        }

        order.setSubtotalAmount(subtotal);

        // Step 3: Apply coupon if provided
        BigDecimal discount = BigDecimal.ZERO;
        if (request.getCouponCode() != null && !request.getCouponCode().isBlank()) {
            Coupon coupon = couponRepository.findByCodeAndIsActiveTrue(request.getCouponCode())
                .orElseThrow(() -> new InvalidCouponException("Invalid or expired coupon code"));

            LocalDateTime now = LocalDateTime.now();
            if (now.isBefore(coupon.getValidFrom()) || now.isAfter(coupon.getValidUntil())) {
                throw new InvalidCouponException("This coupon is not valid at this time");
            }
            if (coupon.getUsageLimit() != null && coupon.getTimesUsed() >= coupon.getUsageLimit()) {
                throw new InvalidCouponException("This coupon has reached its usage limit");
            }

            discount = subtotal.multiply(coupon.getDiscountPercent())
                .divide(BigDecimal.valueOf(100), 2, RoundingMode.HALF_UP);

            if (coupon.getMaxDiscountAmount() != null && discount.compareTo(coupon.getMaxDiscountAmount()) > 0) {
                discount = coupon.getMaxDiscountAmount();
            }

            coupon.setTimesUsed(coupon.getTimesUsed() + 1);
            couponRepository.save(coupon);
            order.setCoupon(coupon);
        }
        order.setDiscountAmount(discount);

        // Step 4: Calculate shipping (free above threshold)
        BigDecimal afterDiscount = subtotal.subtract(discount);
        BigDecimal shippingFee = afterDiscount.compareTo(FREE_SHIPPING_THRESHOLD) >= 0
            ? BigDecimal.ZERO
            : FLAT_SHIPPING_FEE;
        order.setShippingFee(shippingFee);

        // Step 5: Final total
        order.setTotalAmount(afterDiscount.add(shippingFee));
        order.setStatus(Order.OrderStatus.PENDING);

        Order savedOrder = orderRepository.save(order);

        // Step 6: Empty the cart now that the order has captured everything it needs
        cart.getItems().clear();
        cartRepository.save(cart);

        return savedOrder;
    }

    @Transactional
    public Order updateStatus(Long orderId, Order.OrderStatus newStatus) {
        Order order = orderRepository.findById(orderId)
            .orElseThrow(() -> new ResourceNotFoundException("Order not found: " + orderId));
        order.transitionTo(newStatus); // uses the state machine guard from Section 11.4
        return orderRepository.save(order);
    }
}
```

> **Why is the entire `placeOrder` method wrapped in `@Transactional`?** Imagine stock is deducted successfully for item 1, but then item 2 fails because it's out of stock. Without a transaction, item 1's stock deduction would be permanently saved even though the order never completed — a customer would see stock silently vanish with no order to show for it. `@Transactional` guarantees **all-or-nothing**: if any exception is thrown anywhere inside the method, Spring automatically rolls back every database change made during that method call.

> **Why re-check stock at order time even though we checked it at "add to cart" time?** Because time passes between adding to cart and checking out — someone else could buy the last unit in between. This is a classic **race condition**, and re-validating right before the irreversible action (deducting stock) is the standard defensive pattern. Mentioning this explicitly in an interview is a strong signal of real engineering maturity.

### 15.4 `ProductService.java`

```java
package com.shopsphere.service;

import com.shopsphere.dto.request.ProductCreateRequest;
import com.shopsphere.dto.response.ProductResponse;
import com.shopsphere.entity.Category;
import com.shopsphere.entity.Product;
import com.shopsphere.exception.ResourceNotFoundException;
import com.shopsphere.mapper.ProductMapper;
import com.shopsphere.repository.CategoryRepository;
import com.shopsphere.repository.ProductRepository;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.math.BigDecimal;

@Service
public class ProductService {

    private final ProductRepository productRepository;
    private final CategoryRepository categoryRepository;
    private final ProductMapper productMapper;

    public ProductService(ProductRepository productRepository, CategoryRepository categoryRepository,
                           ProductMapper productMapper) {
        this.productRepository = productRepository;
        this.categoryRepository = categoryRepository;
        this.productMapper = productMapper;
    }

    @Transactional(readOnly = true)
    public Page<ProductResponse> search(String keyword, Long categoryId, BigDecimal minPrice,
                                         BigDecimal maxPrice, Pageable pageable) {
        return productRepository.search(keyword, categoryId, minPrice, maxPrice, pageable)
            .map(productMapper::toResponse);
    }

    @Transactional(readOnly = true)
    public ProductResponse getBySlug(String slug) {
        Product product = productRepository.findBySlugAndActiveTrue(slug)
            .orElseThrow(() -> new ResourceNotFoundException("Product not found: " + slug));
        return productMapper.toResponse(product);
    }

    @Transactional
    public ProductResponse create(ProductCreateRequest request) {
        Category category = categoryRepository.findById(request.getCategoryId())
            .orElseThrow(() -> new ResourceNotFoundException("Category not found"));

        Product product = new Product();
        product.setCategory(category);
        product.setName(request.getName());
        product.setSlug(toSlug(request.getName()));
        product.setDescription(request.getDescription());
        product.setPrice(request.getPrice());
        product.setDiscountPrice(request.getDiscountPrice());
        product.setStockQuantity(request.getStockQuantity());
        product.setBrand(request.getBrand());

        Product saved = productRepository.save(product);
        return productMapper.toResponse(saved);
    }

    private String toSlug(String name) {
        return name.toLowerCase().trim().replaceAll("[^a-z0-9]+", "-") + "-" + System.currentTimeMillis() % 10000;
    }
}
```

---

## 16. Project 1: Backend — Controllers (REST API)

**In simple words:** Controllers are the "front desk." They receive HTTP requests, extract the current logged-in user (if any), call the right service, and return an HTTP response with the right status code. Controllers should have almost no logic — if you find yourself writing an `if` statement with business meaning inside a controller, it belongs in a service instead.

### 16.1 `AuthController.java`

```java
package com.shopsphere.controller;

import com.shopsphere.dto.request.LoginRequest;
import com.shopsphere.dto.request.RegisterRequest;
import com.shopsphere.dto.response.AuthResponse;
import com.shopsphere.service.AuthService;
import jakarta.validation.Valid;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/v1/auth")
public class AuthController {

    private final AuthService authService;

    public AuthController(AuthService authService) {
        this.authService = authService;
    }

    @PostMapping("/register")
    public ResponseEntity<AuthResponse> register(@Valid @RequestBody RegisterRequest request) {
        AuthResponse response = authService.register(request);
        return ResponseEntity.status(HttpStatus.CREATED).body(response);
    }

    @PostMapping("/login")
    public ResponseEntity<AuthResponse> login(@Valid @RequestBody LoginRequest request) {
        return ResponseEntity.ok(authService.login(request));
    }
}
```

### 16.2 `ProductController.java`

```java
package com.shopsphere.controller;

import com.shopsphere.dto.response.ProductResponse;
import com.shopsphere.service.ProductService;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.data.web.PageableDefault;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.math.BigDecimal;

@RestController
@RequestMapping("/api/v1/products")
public class ProductController {

    private final ProductService productService;

    public ProductController(ProductService productService) {
        this.productService = productService;
    }

    @GetMapping
    public ResponseEntity<Page<ProductResponse>> search(
            @RequestParam(required = false) String keyword,
            @RequestParam(required = false) Long categoryId,
            @RequestParam(required = false) BigDecimal minPrice,
            @RequestParam(required = false) BigDecimal maxPrice,
            @PageableDefault(size = 20, sort = "id") Pageable pageable) {
        return ResponseEntity.ok(productService.search(keyword, categoryId, minPrice, maxPrice, pageable));
    }

    @GetMapping("/{slug}")
    public ResponseEntity<ProductResponse> getBySlug(@PathVariable String slug) {
        return ResponseEntity.ok(productService.getBySlug(slug));
    }
}
```

### 16.3 `CartController.java`

```java
package com.shopsphere.controller;

import com.shopsphere.dto.request.AddToCartRequest;
import com.shopsphere.entity.Cart;
import com.shopsphere.security.CustomUserPrincipal;
import com.shopsphere.service.CartService;
import jakarta.validation.Valid;
import org.springframework.http.ResponseEntity;
import org.springframework.security.core.annotation.AuthenticationPrincipal;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/v1/cart")
public class CartController {

    private final CartService cartService;

    public CartController(CartService cartService) {
        this.cartService = cartService;
    }

    @GetMapping
    public ResponseEntity<Cart> getCart(@AuthenticationPrincipal CustomUserPrincipal principal) {
        return ResponseEntity.ok(cartService.getCart(principal.getId()));
    }

    @PostMapping("/items")
    public ResponseEntity<Cart> addItem(@AuthenticationPrincipal CustomUserPrincipal principal,
                                         @Valid @RequestBody AddToCartRequest request) {
        return ResponseEntity.ok(cartService.addItem(principal.getId(), request));
    }

    @DeleteMapping("/items/{productId}")
    public ResponseEntity<Cart> removeItem(@AuthenticationPrincipal CustomUserPrincipal principal,
                                            @PathVariable Long productId) {
        return ResponseEntity.ok(cartService.removeItem(principal.getId(), productId));
    }
}
```

### 16.4 `OrderController.java`

```java
package com.shopsphere.controller;

import com.shopsphere.dto.request.PlaceOrderRequest;
import com.shopsphere.entity.Order;
import com.shopsphere.security.CustomUserPrincipal;
import com.shopsphere.service.OrderService;
import jakarta.validation.Valid;
import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.security.core.annotation.AuthenticationPrincipal;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/v1/orders")
public class OrderController {

    private final OrderService orderService;

    public OrderController(OrderService orderService) {
        this.orderService = orderService;
    }

    @PostMapping
    public ResponseEntity<Order> placeOrder(@AuthenticationPrincipal CustomUserPrincipal principal,
                                             @Valid @RequestBody PlaceOrderRequest request) {
        Order order = orderService.placeOrder(principal.getId(), request);
        return ResponseEntity.status(HttpStatus.CREATED).body(order);
    }
}
```

### 16.5 `AdminController.java`

```java
package com.shopsphere.controller;

import com.shopsphere.dto.request.ProductCreateRequest;
import com.shopsphere.dto.response.ProductResponse;
import com.shopsphere.entity.Order;
import com.shopsphere.service.OrderService;
import com.shopsphere.service.ProductService;
import jakarta.validation.Valid;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

@RestController
@RequestMapping("/api/v1/admin")
public class AdminController {

    private final ProductService productService;
    private final OrderService orderService;

    public AdminController(ProductService productService, OrderService orderService) {
        this.productService = productService;
        this.orderService = orderService;
    }

    @PostMapping("/products")
    public ResponseEntity<ProductResponse> createProduct(@Valid @RequestBody ProductCreateRequest request) {
        return ResponseEntity.status(HttpStatus.CREATED).body(productService.create(request));
    }

    @PutMapping("/orders/{orderId}/status")
    public ResponseEntity<Order> updateOrderStatus(@PathVariable Long orderId,
                                                     @RequestParam Order.OrderStatus status) {
        return ResponseEntity.ok(orderService.updateStatus(orderId, status));
    }
}
```

> Note that `AdminController` endpoints are automatically protected by the `.requestMatchers("/api/v1/admin/**").hasRole("ADMIN")` rule configured in `SecurityConfig` (Section 14.3) — the controller itself doesn't need to check the role manually. This is called **declarative security** and is far less error-prone than scattering `if (user.isAdmin())` checks throughout your code.

---

## 17. Project 1: Backend — Exception Handling

**In simple words:** Instead of letting Java's raw, ugly stack traces leak to the frontend (which looks unprofessional and can leak sensitive info), we catch every exception in one central place and turn it into a clean, consistent JSON error response.

```java
package com.shopsphere.exception;

import com.shopsphere.dto.response.ApiErrorResponse;
import jakarta.servlet.http.HttpServletRequest;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.security.authentication.BadCredentialsException;
import org.springframework.validation.FieldError;
import org.springframework.web.bind.MethodArgumentNotValidException;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.RestControllerAdvice;

import java.time.LocalDateTime;
import java.util.HashMap;
import java.util.Map;

@RestControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(ResourceNotFoundException.class)
    public ResponseEntity<ApiErrorResponse> handleNotFound(ResourceNotFoundException ex, HttpServletRequest req) {
        return build(HttpStatus.NOT_FOUND, ex.getMessage(), req);
    }

    @ExceptionHandler(InsufficientStockException.class)
    public ResponseEntity<ApiErrorResponse> handleStock(InsufficientStockException ex, HttpServletRequest req) {
        return build(HttpStatus.CONFLICT, ex.getMessage(), req);
    }

    @ExceptionHandler(InvalidCouponException.class)
    public ResponseEntity<ApiErrorResponse> handleCoupon(InvalidCouponException ex, HttpServletRequest req) {
        return build(HttpStatus.BAD_REQUEST, ex.getMessage(), req);
    }

    @ExceptionHandler(DuplicateEmailException.class)
    public ResponseEntity<ApiErrorResponse> handleDuplicateEmail(DuplicateEmailException ex, HttpServletRequest req) {
        return build(HttpStatus.CONFLICT, ex.getMessage(), req);
    }

    @ExceptionHandler(BadCredentialsException.class)
    public ResponseEntity<ApiErrorResponse> handleBadCredentials(BadCredentialsException ex, HttpServletRequest req) {
        return build(HttpStatus.UNAUTHORIZED, "Invalid email or password", req);
    }

    @ExceptionHandler(MethodArgumentNotValidException.class)
    public ResponseEntity<Map<String, Object>> handleValidation(MethodArgumentNotValidException ex,
                                                                   HttpServletRequest req) {
        Map<String, String> fieldErrors = new HashMap<>();
        for (FieldError error : ex.getBindingResult().getFieldErrors()) {
            fieldErrors.put(error.getField(), error.getDefaultMessage());
        }
        Map<String, Object> body = new HashMap<>();
        body.put("status", HttpStatus.BAD_REQUEST.value());
        body.put("error", "Validation Failed");
        body.put("fieldErrors", fieldErrors);
        body.put("path", req.getRequestURI());
        body.put("timestamp", LocalDateTime.now());
        return ResponseEntity.badRequest().body(body);
    }

    @ExceptionHandler(Exception.class)
    public ResponseEntity<ApiErrorResponse> handleGeneric(Exception ex, HttpServletRequest req) {
        // Log the full stack trace server-side, but never expose internals to the client
        return build(HttpStatus.INTERNAL_SERVER_ERROR, "An unexpected error occurred. Please try again later.", req);
    }

    private ResponseEntity<ApiErrorResponse> build(HttpStatus status, String message, HttpServletRequest req) {
        ApiErrorResponse error = ApiErrorResponse.builder()
            .status(status.value())
            .error(status.getReasonPhrase())
            .message(message)
            .path(req.getRequestURI())
            .timestamp(LocalDateTime.now())
            .build();
        return ResponseEntity.status(status).body(error);
    }
}
```

**Example custom exceptions (simple, one-liners):**

```java
package com.shopsphere.exception;

public class ResourceNotFoundException extends RuntimeException {
    public ResourceNotFoundException(String message) { super(message); }
}
```

```java
package com.shopsphere.exception;

public class InsufficientStockException extends RuntimeException {
    public InsufficientStockException(String message) { super(message); }
}
```

```java
package com.shopsphere.exception;

public class InvalidCouponException extends RuntimeException {
    public InvalidCouponException(String message) { super(message); }
}
```

```java
package com.shopsphere.exception;

public class DuplicateEmailException extends RuntimeException {
    public DuplicateEmailException(String message) { super(message); }
}
```

> **Why `@RestControllerAdvice` instead of try/catch in every controller method?** Without it, you would repeat the same try/catch blocks in every single controller — a massive violation of the **DRY principle** (Don't Repeat Yourself). `@RestControllerAdvice` applies globally, across every controller in the application, from one place.

---

## 18. Project 1: Backend — Payments Integration (Stripe)

**In simple words:** Stripe is a company that handles the scary, regulated parts of accepting money (card numbers, bank compliance, fraud detection) so you never have to touch raw card data yourself. Your backend never sees a credit card number — instead, Stripe gives you a "Payment Intent," your frontend collects card details using Stripe's own secure widget, and Stripe tells your backend "yes, this succeeded" or "no, it failed."

**Why this matters for interviews:** Handling money is one of the highest-stakes parts of any real system, and demonstrating that you know *not* to touch raw card numbers yourself (PCI-DSS compliance concerns) is a strong signal of security awareness.

### 18.1 `StripeConfig.java`

```java
package com.shopsphere.config;

import com.stripe.Stripe;
import jakarta.annotation.PostConstruct;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.context.annotation.Configuration;

@Configuration
public class StripeConfig {

    @Value("${app.stripe.secret-key}")
    private String secretKey;

    @PostConstruct
    public void init() {
        Stripe.apiKey = secretKey;
    }
}
```

### 18.2 `PaymentService.java`

```java
package com.shopsphere.service;

import com.shopsphere.entity.Order;
import com.shopsphere.entity.Payment;
import com.shopsphere.exception.ResourceNotFoundException;
import com.shopsphere.repository.OrderRepository;
import com.shopsphere.repository.PaymentRepository;
import com.stripe.exception.StripeException;
import com.stripe.model.PaymentIntent;
import com.stripe.param.PaymentIntentCreateParams;
import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;

import java.math.BigDecimal;

@Service
public class PaymentService {

    private final OrderRepository orderRepository;
    private final PaymentRepository paymentRepository;

    public PaymentService(OrderRepository orderRepository, PaymentRepository paymentRepository) {
        this.orderRepository = orderRepository;
        this.paymentRepository = paymentRepository;
    }

    /**
     * Step 1 of payment flow: create a Stripe PaymentIntent and return its
     * "client secret" to the frontend. The frontend uses this secret with
     * Stripe.js to securely collect card details — your server never sees them.
     */
    @Transactional
    public String createPaymentIntent(Long orderId) throws StripeException {
        Order order = orderRepository.findById(orderId)
            .orElseThrow(() -> new ResourceNotFoundException("Order not found: " + orderId));

        long amountInSmallestUnit = order.getTotalAmount()
            .multiply(BigDecimal.valueOf(100)) // Stripe expects amounts in paise/cents
            .longValueExact();

        PaymentIntentCreateParams params = PaymentIntentCreateParams.builder()
            .setAmount(amountInSmallestUnit)
            .setCurrency("inr")
            .putMetadata("orderId", String.valueOf(order.getId()))
            .setAutomaticPaymentMethods(
                PaymentIntentCreateParams.AutomaticPaymentMethods.builder()
                    .setEnabled(true)
                    .build()
            )
            .build();

        PaymentIntent intent = PaymentIntent.create(params);

        Payment payment = new Payment();
        payment.setOrder(order);
        payment.setProvider("STRIPE");
        payment.setProviderPaymentId(intent.getId());
        payment.setStatus(Payment.PaymentStatus.PENDING);
        payment.setAmount(order.getTotalAmount());
        paymentRepository.save(payment);

        return intent.getClientSecret();
    }

    /**
     * Step 2 of payment flow: Stripe calls this webhook automatically when a
     * payment succeeds or fails. We NEVER trust the frontend to tell us "payment
     * succeeded" directly — that would let anyone fake a successful order for free.
     * Only Stripe's signed webhook event is trusted.
     */
    @Transactional
    public void handleWebhookEvent(String paymentIntentId, boolean succeeded) {
        Payment payment = paymentRepository.findByProviderPaymentId(paymentIntentId)
            .orElseThrow(() -> new ResourceNotFoundException("Payment record not found"));

        payment.setStatus(succeeded ? Payment.PaymentStatus.SUCCESS : Payment.PaymentStatus.FAILED);
        paymentRepository.save(payment);

        Order order = payment.getOrder();
        if (succeeded) {
            order.transitionTo(Order.OrderStatus.CONFIRMED);
            orderRepository.save(order);
        }
    }
}
```

### 18.3 `PaymentController.java` (including the webhook endpoint)

```java
package com.shopsphere.controller;

import com.shopsphere.service.PaymentService;
import com.stripe.exception.SignatureVerificationException;
import com.stripe.model.Event;
import com.stripe.model.PaymentIntent;
import com.stripe.net.Webhook;
import jakarta.servlet.http.HttpServletRequest;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.util.Map;

@RestController
@RequestMapping("/api/v1/payments")
public class PaymentController {

    private final PaymentService paymentService;

    @Value("${app.stripe.webhook-secret}")
    private String webhookSecret;

    public PaymentController(PaymentService paymentService) {
        this.paymentService = paymentService;
    }

    @PostMapping("/create-intent/{orderId}")
    public ResponseEntity<Map<String, String>> createIntent(@PathVariable Long orderId) throws Exception {
        String clientSecret = paymentService.createPaymentIntent(orderId);
        return ResponseEntity.ok(Map.of("clientSecret", clientSecret));
    }

    @PostMapping("/webhook")
    public ResponseEntity<Void> webhook(@RequestBody String payload,
                                         @RequestHeader("Stripe-Signature") String sigHeader) {
        try {
            Event event = Webhook.constructEvent(payload, sigHeader, webhookSecret);
            if ("payment_intent.succeeded".equals(event.getType())) {
                PaymentIntent intent = (PaymentIntent) event.getDataObjectDeserializer().getObject().orElseThrow();
                paymentService.handleWebhookEvent(intent.getId(), true);
            } else if ("payment_intent.payment_failed".equals(event.getType())) {
                PaymentIntent intent = (PaymentIntent) event.getDataObjectDeserializer().getObject().orElseThrow();
                paymentService.handleWebhookEvent(intent.getId(), false);
            }
            return ResponseEntity.ok().build();
        } catch (SignatureVerificationException e) {
            // If the signature doesn't match, this request did NOT genuinely come from Stripe — reject it
            return ResponseEntity.status(HttpStatus.BAD_REQUEST).build();
        }
    }
}
```

> **Why verify the webhook signature?** Anyone on the internet could send a POST request to `/api/v1/payments/webhook` claiming "payment succeeded!" Stripe signs every webhook request with a secret only you and Stripe know, so `Webhook.constructEvent()` throws an exception if the request wasn't genuinely sent by Stripe. Skipping this check is a critical security vulnerability that would let anyone get free orders.

---

## 19. Project 1: Backend — application.yml and Configuration

```yaml
# application.yml (shared defaults)
spring:
  application:
    name: shopsphere-backend
  jpa:
    hibernate:
      ddl-auto: validate   # NEVER use 'update' or 'create' in real apps — use Flyway migrations instead
    show-sql: false
    properties:
      hibernate:
        format_sql: true
  flyway:
    enabled: true
    locations: classpath:db/migration
  servlet:
    multipart:
      max-file-size: 5MB
      max-request-size: 5MB

server:
  port: 8080
  error:
    include-message: never   # never leak raw exception messages in default Spring error responses

app:
  jwt:
    secret: ${JWT_SECRET}              # injected via environment variable, NEVER hardcoded
    expiration-ms: 86400000            # 24 hours
  stripe:
    secret-key: ${STRIPE_SECRET_KEY}
    webhook-secret: ${STRIPE_WEBHOOK_SECRET}
  cors:
    allowed-origins: ${FRONTEND_URL:http://localhost:5173}

springdoc:
  swagger-ui:
    path: /swagger-ui.html
  api-docs:
    path: /v3/api-docs
```

```yaml
# application-dev.yml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/shopsphere
    username: postgres
    password: postgres
  jpa:
    show-sql: true

logging:
  level:
    com.shopsphere: DEBUG
    org.springframework.security: DEBUG
```

```yaml
# application-prod.yml
spring:
  datasource:
    url: ${DATABASE_URL}
    username: ${DATABASE_USERNAME}
    password: ${DATABASE_PASSWORD}
    hikari:
      maximum-pool-size: 10

logging:
  level:
    com.shopsphere: INFO
    root: WARN
```

> **Why `ddl-auto: validate` instead of `update`?** `update` silently modifies your production database schema based on your Java entities — this is convenient in tutorials but dangerous in real systems (it can silently drop columns, and it makes schema changes untracked and unreviewable). Using **Flyway** migrations (versioned `.sql` files like `V1__init_schema.sql`) means every schema change is an explicit, reviewable, version-controlled file — exactly like how you version control application code. `ddl-auto: validate` just double-checks your entities match what Flyway already created, catching mistakes early.

> **Why are secrets like `JWT_SECRET` and `STRIPE_SECRET_KEY` read from environment variables (`${...}`) instead of written directly in the YAML file?** This is the **12-Factor App** principle of "config in the environment, not in code." It means: (1) secrets never get committed to Git and leaked publicly, and (2) you can use the exact same build artifact across dev/staging/prod, just changing environment variables — you never rebuild the app just to point it at a different database.

---

## 20. Project 1: Full REST API Reference Table

| Method | Endpoint | Auth Required | Description |
|---|---|---|---|
| POST | `/api/v1/auth/register` | No | Create a new customer account |
| POST | `/api/v1/auth/login` | No | Log in, returns JWT token |
| GET | `/api/v1/products` | No | Search/list products (paginated, filterable) |
| GET | `/api/v1/products/{slug}` | No | Get single product details |
| GET | `/api/v1/cart` | Yes (Customer) | Get current user's cart |
| POST | `/api/v1/cart/items` | Yes (Customer) | Add item to cart |
| DELETE | `/api/v1/cart/items/{productId}` | Yes (Customer) | Remove item from cart |
| POST | `/api/v1/orders` | Yes (Customer) | Place an order from the current cart |
| GET | `/api/v1/orders` | Yes (Customer) | List current user's past orders (paginated) |
| GET | `/api/v1/orders/{id}` | Yes (Customer) | Get a specific order's details |
| POST | `/api/v1/payments/create-intent/{orderId}` | Yes (Customer) | Create a Stripe payment intent for an order |
| POST | `/api/v1/payments/webhook` | No (Stripe-signed) | Stripe payment status callback |
| POST | `/api/v1/reviews` | Yes (Customer) | Submit a product review (must be verified purchase) |
| POST | `/api/v1/admin/products` | Yes (Admin) | Create a new product |
| PUT | `/api/v1/admin/products/{id}` | Yes (Admin) | Update an existing product |
| DELETE | `/api/v1/admin/products/{id}` | Yes (Admin) | Soft-delete (deactivate) a product |
| GET | `/api/v1/admin/orders` | Yes (Admin) | List all orders across all customers |
| PUT | `/api/v1/admin/orders/{id}/status` | Yes (Admin) | Update an order's status |
| POST | `/api/v1/admin/coupons` | Yes (Admin) | Create a discount coupon |

**Standard pagination query parameters** (used on every list endpoint):

```
GET /api/v1/products?page=0&size=20&sort=price,asc
```

**Standard success response envelope for a paginated list:**

```json
{
  "content": [ /* array of items */ ],
  "totalElements": 143,
  "totalPages": 8,
  "number": 0,
  "size": 20,
  "first": true,
  "last": false
}
```

---




