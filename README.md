Step 2: Start Services
Open XAMPP Control Panel and start:

Apache
MySQL

Step 3: Copy Project
Copy the project into:

C:\xampp\htdocs\

The final path should be:

C:\xampp\htdocs\student-management\

Step 4: Create Database
Open:

http://localhost/phpmyadmin

Create/import the database using:

database/database.sql

The SQL file automatically creates:

student_management

and its required tables.

9. Database Configuration
Open:

config/database.php

Default XAMPP configuration:

private string $host = "localhost";
private string $database = "student_management";
private string $username = "root";
private string $password = "";

If your MySQL installation uses a password, update the password value.

10. Run the Application
After starting Apache and MySQL, open:

http://localhost/student-management/public/

The request is processed as:

Browser
   ↓
public/index.php
   ↓
routes/web.php
   ↓
Controller
   ↓
Model
   ↓
MySQL
   ↓
Model
   ↓
Controller
   ↓
View
   ↓
Browser

11. Example Student Operations
View Students
http://localhost/student-management/public/index.php?action=students

Add Student
http://localhost/student-management/public/index.php?action=create_student

Delete Student
http://localhost/student-management/public/index.php?action=delete_student&id=1

12. Security
The application uses the following security practices:

PDO prepared statements

Input validation

HTML output escaping

Session-based authentication

Role-based authorization

Password hashing

Database foreign-key constraints

Passwords should never be stored as plain text.

Use:

password_hash($password, PASSWORD_DEFAULT);

for storing passwords.

Use:

password_verify($password, $hashedPassword);

for checking passwords.

13. ER Diagram
The complete ER diagram is available in:

database/er-diagram.md

The main entities are:

Users
Students
Courses
Enrollments
Attendance
Marks

14. User Flow
Admin
Login
  ↓
Dashboard
  ↓
Manage Students
  ↓
Manage Courses
  ↓
Manage Teachers
  ↓
View Reports
  ↓
Logout

Teacher
Login
  ↓
Dashboard
  ↓
Select Course
  ↓
View Students
  ↓
Mark Attendance
  ↓
Enter Marks
  ↓
Logout

Student
Login
  ↓
Dashboard
  ↓
View Profile
  ↓
View Courses
  ↓
View Attendance
  ↓
View Marks
  ↓
Logout

15. API / Request Structure
The application uses HTTP requests handled by the router.

Example:

GET
?action=students

is routed to:

$studentController->index();

Creating a student:

POST
?action=create_student

is handled by:

$studentController->create();

Deleting a student:

GET
?action=delete_student&id=1

is handled by:

$studentController->delete();

16. CRUD Operations
The application supports CRUD operations.

C - Create
R - Read
U - Update
D - Delete

Example for students:

Create Student
      ↓
Read Student
      ↓
Update Student
      ↓
Delete Student

17. Development Requirements
Minimum requirements:

PHP 8.0+
MySQL 5.7+
Apache 2.4+
XAMPP
Modern Web Browser

Recommended:

PHP 8.1+
MySQL 8+
XAMPP
VS Code
Google Chrome / Firefox / Edge

18. Troubleshooting
Database Connection Error
Check:

MySQL is running
Database name is correct
Username is correct
Password is correct

Check:

config/database.php

Page Not Found
Make sure the project is located at:

C:\xampp\htdocs\student-management\

and access it using:

http://localhost/student-management/public/

Table Does Not Exist
Import:

database/database.sql

through phpMyAdmin.

19. Future Enhancements
Possible future improvements include:

REST API

Email notifications

PDF report generation

Student profile pictures

Advanced search

Pagination

Attendance percentage calculation

Grade calculation

Admin analytics dashboard

Password reset

Two-factor authentication

Cloud deployment

20. License
This project is developed for educational and academic purposes.

21. Author
Project Name    : Student Management System
Architecture    : MVC
Backend         : PHP
Database        : MySQL
Frontend        : HTML / CSS / JavaScript

Quick Start
1. Install XAMPP
2. Start Apache and MySQL
3. Copy project to C:\xampp\htdocs\
4. Open phpMyAdmin
5. Import database/database.sql
6. Open the application in a browser
7. Start managing students

Application URL:

http://localhost/student-management/public/
