📚 Library Management System
🔎 Introduction

The Library Management System is a simple Java + MySQL application built to streamline library operations. It allows administrators to manage book inventory, borrower records, and track book lending/returns efficiently. The project demonstrates the use of Object-Oriented Programming, JDBC, and relational database management.

📂 Contents

Key Features

Tech Stack

Installation & Setup

How to Use

✅ Key Features

📘 Book Inventory

Add, edit, delete, and search books.

View complete book listings.

Track available copies.

👤 Borrower Records

Add or remove borrower details.

Display borrower list.

🔄 Book Lending System

Issue books to borrowers.

Return books and update stock.

Maintain due dates and lending history.

🗄️ Database Integration

MySQL database stores book and borrower data.

JDBC is used to establish database connectivity.

🛠 Tech Stack

Java – Core programming logic

MySQL – Database to store records

JDBC – Database connectivity

⚙ Installation & Setup

Clone this repository

git clone https://github.com/yourusername/LibraryManagementSys.git
cd LibraryManagementSys


Set up MySQL database

CREATE DATABASE librarymanagement;
USE librarymanagement;

CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author VARCHAR(255) NOT NULL,
    isbn VARCHAR(20),
    genre VARCHAR(50),
    quantity INT NOT NULL
);

CREATE TABLE borrowers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    contact_details VARCHAR(255)
);

CREATE TABLE borrowed_books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    borrower_id INT,
    book_id INT,
    due_date DATE,
    FOREIGN KEY (borrower_id) REFERENCES borrowers(id),
    FOREIGN KEY (book_id) REFERENCES books(id)
);


Update DB credentials in DBHelper.java

private static final String URL = "jdbc:mysql://localhost:3306/librarymanagement";
private static final String USER = "root";   // replace with your username
private static final String PASSWORD = "password";  // replace with your password


Compile & Run

Open in VS Code / IntelliJ / Eclipse.

Build and run the main program.

▶ How to Use

View Books → List all available books.

Add Book → Insert new book records.

Delete Book → Remove books from inventory.

Search Book → Look up books by title.

Manage Borrowers → Add/remove borrower details.

Borrow / Return Books → Track issued and returned books with due dates.

🚀 Future Scope

Add a GUI using JavaFX or Swing.

Include login system (Admin/User roles).

Generate borrowing history reports.
