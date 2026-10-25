Student Registration Java EE Application
A lightweight, classic Java Servlet-based web application for managing student registrations, utilizing JDBC for MySQL database connectivity.

Features
Student Registration Form: Simple web interface to capture student names and email addresses.

Servlet Controller: Handles HTTP GET requests to render the form and POST requests to process submissions securely using PreparedStatement to prevent SQL injection.

Database Integration: Centralized MySQL connection utility (DBConnection) using JDBC.

Tech Stack
Language: Java (JDK 8+)
Web Technology: Java Servlets (javax.servlet)
Database: MySQL
Build / Server Environment: Compatible with standard Servlet containers (e.g., Apache Tomcat)
Project Structure
src/
└── com/
    ├── controller/
    │   └── StudentController.java    # Handles HTTP GET & POST requests[cite: 3]
    └── util/
        └── DBConnection.java         # Manages MySQL database connections[cite: 1]
WebContent/ (or webapp/)
└── index.html                        # Frontend registration form[cite: 2]

Getting Started
1. Prerequisites
Java Development Kit (JDK) installed.
Apache Tomcat (or any compatible Servlet container).
MySQL Server installed and running.
2. Database Setup
Create a database named studentdb and set up the students table:

CREATE DATABASE studentdb;

USE studentdb;

CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL
);
3. Configuration
Update your database credentials in src/com/example/util/DBConnection.java if they differ from the defaults:

private static final String URL = "jdbc:mysql://localhost:3306/studentdb";
private static final String USER = "root";
private static final String PASS = "your_password";
4. Running the Application
Import the project into your preferred Java IDE (such as Eclipse or IntelliJ IDEA).
Configure the project facets to include Dynamic Web Module and add the MySQL JDBC driver (mysql-connector-java) to your project's classpath/lib.
Deploy the project to your Apache Tomcat server.
Open your browser and navigate to:
http://localhost:8080/YourProjectName/student
