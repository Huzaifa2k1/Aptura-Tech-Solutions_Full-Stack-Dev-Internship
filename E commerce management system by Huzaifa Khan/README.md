# E-Commerce Web Application (React & Node.js)

A modern, full-stack E-Commerce application designed for high performance, scalability, and secure online shopping.

---

## 📌 Project Overview

This project is a full-featured E-Commerce platform built using **React** for the dynamic user interface and a robust backend database structure designed to handle high-volume traffic (**1,000,000+ products** and **500,000+ users**). 

The platform includes product catalog management, category filtering, cart operations, user authentication, and order processing workflows.

---

## 🛠️ Tech Stack & Technologies

* **Frontend:** React.js, JavaScript (ES6+), HTML5, CSS3 / Modern Styling Frameworks
* **State Management & Routing:** React Context API / Redux, React Router
* **Backend / Database Architecture:** Node.js, Express.js, PostgreSQL / MySQL
* **Security Practices:** JWT Authentication, HttpOnly Cookies, Input Sanitization (DOMPurify), Rate Limiting, CORS Policy
* **Styling & Icons:** Styled Components / CSS Modules, Lucide / FontAwesome Icons

---

## 🚀 Key Features

* 🛒 **Dynamic Product Catalog:** Paginated view supporting 1M+ product records with fast category filtering and multi-column sorting.
* 🔍 **Full-Text Product Search:** Optimized indexing for instant product lookups.
* 💳 **Shopping Cart & Checkout Flow:** Real-time state management for item counts, price calculations, and order creation.
* 👤 **User Authentication & Authorization:** Secure user login/signup using hashed credentials (`bcrypt`) and JWT sessions.
* 🔒 **Enterprise-Grade Security:**
  * Prevention of **SQL Injection** via parameterized queries & ORMs.
  * Prevention of **XSS** via React JSX escaping and input sanitization.
  * **CSRF** protection using `SameSite` cookie flags and CORS restriction.

---

## 🗄️ Database Architecture & Design

The database schema is structured up to **Third Normal Form (3NF)** to ensure zero redundancy and fast transactional throughput:

* `users` — Stores customer credentials, roles, and profile attributes.
* `categories` — Hierarchical category arrangement for efficient catalog indexing.
* `products` — Product details linked via indexed Foreign Keys to categories.
* `orders` — Order metadata, user mappings, and status tracking.
* `order_items` — Normalized line-items linking products to specific orders.

### ⚡ Performance Optimization Strategies
1. **B-Tree Indexing:** Primary keys, foreign keys (`category_id`, `user_id`), and composite indexes (`category_id, price`) reduce lookup time from $O(N)$ to $O(\log N)$.
2. **Database Normalization:** Keeps storage footprint lean and accelerates `UPDATE` operations across high-volume inventories.

---

## 🔒 Security Implementations

| Vulnerability | Threat Risk | Prevention Strategy Implemented |
| :--- | :--- | :--- |
| **XSS** (Cross-Site Scripting) | Malicious script execution in client browser | JSX automatic escaping, `DOMPurify`, `HttpOnly` auth cookies |
| **CSRF** (Cross-Site Request Forgery) | Unintended cross-origin actions | `SameSite=Strict/Lax` cookie policy, explicit CORS origins |
| **SQL Injection** | Unauthorized database manipulation | Parameterized SQL queries & ORM abstraction layer |
| **Brute Force Attacks** | Account takeover attempts | Credential hashing (`Bcrypt`) and API rate limiting (`express-rate-limit`) |

---

## ⚙️ Getting Started / Local Setup

### Prerequisites
* **Node.js** (v16.0 or higher)
* **npm** or **yarn**

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/ecommerce-react-app.git
   cd ecommerce-react-app
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Create a `.env` file in the root directory and add:
   ```env
   REACT_APP_API_URL=http://localhost:5000/api
   PORT=5000
   ```

4. **Start the development server:**
   ```bash
   npm start
   ```
   Open `http://localhost:3000` to view the application in your browser.

---

## 📜 License & Acknowledgments

This project was built as part of the Web Development Internship & Technical Evaluation Submission.
