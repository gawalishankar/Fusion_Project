# Fusion Project

Fusion Project is a web-based application developed using modern web technologies with PHP and MySQL as the backend. The project is designed to demonstrate full-stack development along with cloud deployment using AWS services.

---

## 🖥️ Web Technologies Used

Frontend:
- HTML
- CSS
- JavaScript

Backend:
- PHP

Database:
- MySQL

---

## 🛠️ Local Development Setup

### 1️⃣ Clone the Repository

git clone https://github.com/gawalishankar/Fusion_Project.git
cd Fusion_Project/Application

### 2️⃣ Install Local Server

You can use any PHP + MySQL stack:
- XAMPP
- WAMP
- MAMP

Make sure:
- Apache is running
- MySQL is running

### 3️⃣ Database Setup

1. Open phpMyAdmin
2. Create a database (example name: fusion_db)
3. Import SQL file located in project

Example:

fusion_db.sql

### 4️⃣ Configure Database Connection

Edit config/connection file in PHP and set values:

DB_HOST = localhost
DB_USER = root
DB_PASS =
DB_NAME = fusion_db

Or use environment variables:

DB_HOST
DB_USER
DB_PASS
DB_NAME

### 5️⃣ Run Application Locally

Open browser and access:

http://localhost/Fusion_Project/Application/

---
