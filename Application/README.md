Fusion Project — Web Application Development

This folder contains the web application of the Fusion Project, developed using HTML, CSS, JavaScript, PHP, and MySQL.

---

Architecture

Frontend (HTML/CSS/JS) → Backend (PHP) → MySQL Database

---

Prerequisites

PHP 7.x or higher

MySQL Server

Apache / Nginx server (XAMPP, WAMP, MAMP, or LAMP stack)

Git installed

Optional: Docker (for local containerized development)

Step 1: Clone Repository
git clone https://github.com/gawalishankar/Fusion_Project.git
cd Fusion_Project/Application

Step 2: Configure Database

Create a new MySQL database (example: fusion_db)

mysql -u root -p
CREATE DATABASE fusion_db;


Import SQL file:

mysql -u root -p fusion_db < database/fusion_db.sql


Update database connection in config/config.php:

$DB_HOST = 'localhost';
$DB_USER = 'root';
$DB_PASS = '';
$DB_NAME = 'fusion_db';


✅ Optional: Use environment variables for better security:

$DB_HOST = getenv('DB_HOST');
$DB_USER = getenv('DB_USER');
$DB_PASS = getenv('DB_PASS');
$DB_NAME = getenv('DB_NAME');

Step 3: Run Local Development Server

Start Apache and MySQL (XAMPP/WAMP/MAMP)

Navigate to application folder:

http://localhost/Fusion_Project/Application/


Your application should load and connect to the database.

Step 4: Directory Structure
Application/
│
├── assets/         # CSS, JS, images
├── config/         # Database connection and configuration
├── includes/       # Reusable PHP modules
├── pages/          # Application pages (frontend + backend)
├── database/       # SQL scripts for development
└── index.php       # Main entry point

Step 5: Optional — Dockerize Application for Development

Build Docker image:

docker build -t fusion-app .


Run container:

docker run -d -p 8080:80 fusion-app


Open browser:

http://localhost:8080

Step 6: Notes for Development

Ensure PHP mysqli extension is enabled

Use consistent coding standards for PHP, HTML, and JS

Include assets properly in the assets/ folder

Use includes/ for reusable code to reduce duplication
