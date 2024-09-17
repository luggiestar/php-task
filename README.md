# php-task
# Simple Book Management System

This project is a **Simple Book Management System** built with PHP, MySQL, and HTML. The system allows users to manage their personal book collections. It includes user authentication (login, registration) and role-based authorization, where regular users can manage only their own books, and admins have the privilege to manage all books and users.

## Features

### User Authentication
- **Registration**: Users can register to create an account.
- **Login**: Users can log in to manage books.
- **Logout**: Users can securely log out of the system.

### User Authorization
- **Regular Users**: Can add, edit, and delete only their own books.
- **Admins**: Can view, edit, and delete all books, and also manage users.

### Book Management (CRUD)
- **Add Books**: Users can add new books with the following details:
  - Title
  - Author
  - Genre
  - Year of Publication
- **Edit Books**: Users can edit the details of the books they have added.
- **Delete Books**: Users can delete books, but only the books they have added. Admins can delete any book.
- **View Books**: All users can view a list of books, with details like title, author, genre, and year.

## Database Structure

The project uses a MySQL database with the following structure:

### 1. Users Table
Stores user information, including user roles (regular user or admin).
```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(100) NOT NULL,
  email VARCHAR(100) NOT NULL UNIQUE,
  password VARCHAR(255) NOT NULL,
  role ENUM('user', 'admin') DEFAULT 'user',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
