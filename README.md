# 📚 Book Inventory and Order Tracking System

This project is a simple relational database for managing a book store. It tracks books in stock, customer details, and orders placed. The database is designed using standard SQL (PostgreSQL syntax) with a focus on clarity, referential integrity, and useful reporting queries.

---

## 🗃️ Database Schema

### 📘 `Books`
Stores all available books in the inventory.

| Column         | Type           | Description                 |
|----------------|----------------|-----------------------------|
| Book_ID        | SERIAL (PK)    | Unique ID for each book     |
| Title          | VARCHAR(100)   | Book title                  |
| Author         | VARCHAR(100)   | Book author                 |
| Genre          | VARCHAR(50)    | Genre (e.g., Fiction, Sci-Fi)|
| Published_Year | INT            | Year of publication         |
| Price          | NUMERIC(10, 2) | Book price                  |
| Stock          | INT            | Number of copies in stock   |

---

### 👤 `Customers`
Stores customer contact and location information.

| Column      | Type           | Description               |
|-------------|----------------|---------------------------|
| Customer_ID | SERIAL (PK)    | Unique ID for each customer |
| Name        | VARCHAR(100)   | Full name of the customer |
| Email       | VARCHAR(100)   | Email address             |
| Phone       | VARCHAR(15)    | Phone number              |
| City        | VARCHAR(50)    | City of residence         |
| Country     | VARCHAR(150)   | Country                   |

---

### 📦 `Orders`
Stores details of customer orders, including quantity and total amount.

| Column       | Type           | Description                          |
|--------------|----------------|--------------------------------------|
| Order_ID     | SERIAL (PK)    | Unique ID for each order             |
| Customer_ID  | INT (FK)       | Refers to `Customers(Customer_ID)`   |
| Book_ID      | INT (FK)       | Refers to `Books(Book_ID)`           |
| Order_Date   | DATE           | Date of the order                    |
| Quantity     | INT            | Number of books ordered              |
| Total_Amount | NUMERIC(10, 2) | Total price for the ordered books    |



  ✅ Concepts Demonstrated
LEFT JOIN to include books with no orders

COALESCE() to handle NULL values in aggregation

GROUP BY for calculating total ordered quantity per book

FOREIGN KEY constraints for relational integrity

🔧 Setup Instructions
Create a PostgreSQL database.

Run the SQL script to create the tables.

Insert sample data into the Books, Customers, and Orders tables.

Run queries to analyze stock, sales, and customer orders.

📦 Future Enhancements
Add book reviews and ratings

Create stored procedures for order placing and stock update

Add user authentication for admins (if turned into a web app)

Build a front-end using Python (Streamlit/Django/Flask)
