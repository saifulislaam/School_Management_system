# 🎓 School Management System (Web-Based)

A simple **School Management System** built with **PHP, MySQL, HTML, CSS, and JavaScript**, designed for managing student records.

This project runs locally using **XAMPP (Apache + MySQL)** and provides features for adding, editing, deleting, and searching student data.

---

## 📌 Features

* 🔐 Login/Logout system
* ➕ Add new students
* ✏️ Edit student information
* ❌ Delete students by Roll No
* 🔍 Search by **Name, Roll No, or Class**
* 📋 View all students

---

## 🛠️ Requirements

* Linux (tested on Kali / Ubuntu)
* [XAMPP](https://www.apachefriends.org/) with:

  * Apache 2.4+
  * PHP 8+
  * MySQL/MariaDB

---

## 🔧 Installation

1. **Install XAMPP** (if not already installed):

   ```bash
   sudo apt install wget
   wget https://www.apachefriends.org/xampp-files/8.2.12/xampp-linux-x64-8.2.12-0-installer.run
   sudo chmod +x xampp-linux-x64-8.2.12-0-installer.run
   sudo ./xampp-linux-x64-8.2.12-0-installer.run
   ```

2. **Start XAMPP services**:

   ```bash
   sudo /opt/lampp/lampp start
   ```

3. **Move project folder into htdocs**:

   ```bash
   sudo cp -r ~/Desktop/school_system /opt/lampp/htdocs/
   ```

4. **Create `db_connect.php`** in the project folder:

   ```php
   <?php
   $mysqli = new mysqli("localhost", "root", "", "student_db");
   if ($mysqli->connect_error) {
       die("Connection failed: " . $mysqli->connect_error);
   }
   ?>
   ```

---

## 🗄️ Database Setup

1. Open **phpMyAdmin**:

   ```
   http://localhost/phpmyadmin/
   ```

2. Create database:

   ```sql
   CREATE DATABASE student_db;
   ```

3. Create `students` table:

   ```sql
   CREATE TABLE students (
       roll_no INT PRIMARY KEY,
       name VARCHAR(100),
       class VARCHAR(10),
       grade VARCHAR(5),
       email VARCHAR(100)
   );
   ```

4. (Optional) Add a sample student:

   ```sql
   INSERT INTO students (roll_no, name, class, grade, email)
   VALUES (1, 'Ali Khan', '10', 'A', 'ali@example.com');
   ```

---

## ▶️ Usage

1. Visit the project in your browser:

   ```
   http://localhost/school_system/
   ```

2. Login (if enabled), then:

   * Add students
   * Edit or delete existing records
   * Search students by roll no, name, or class

---

## 🤝 Contribution

Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---

## 📜 License

This project is licensed under the **MIT License** — feel free to use and modify.

---

#
