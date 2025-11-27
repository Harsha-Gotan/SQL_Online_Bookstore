# SQL_Online_Bookstore
SQL database for an online bookstore with schema, queries and KPIs.

📚 Online Bookstore SQL Project

A comprehensive relational database system for managing books, customers, and orders in an online bookstore.

## 🏗️ Database Architecture
Three interconnected tables:
- BOOKS : Book details including Book_ID (Primary Key), Title, Author, Genre, Published_Year, Price and Stock
   : <a href="https://github.com/Harsha-Gotan/SQL_Online_Bookstore/blob/main/Books.csv">BOOKS</a>
- CUSTOMER: Customer information including Customer_ID (Primary Key), Name, Email, Phone, City and Country
   : <a href="https://github.com/Harsha-Gotan/SQL_Online_Bookstore/blob/main/Customers.csv">CUSTOMERS</a>
- ORDERS: Order records linking books and customers with Order_Date, Quantity and Total_Amount
   : <a href="https://github.com/Harsha-Gotan/SQL_Online_Bookstore/blob/main/Orders.csv">ORDERS</a>

## ✅ Key Features
- Database schema design
- Data insertion scripts
- Querying:

   - Basic Queries
 1) Retrieve all books in the "Fiction" genre
 2) Find books published after the year 1950
 3) List all customers from the Canada
 4) Show orders placed in November 2023
 5) Retrieve the total stock of books available
 6) Find the details of the most expensive book
 7) Show all customers who ordered more than 1 quantity of a book
 8) Retrieve all orders where the total amount exceeds $20
 9) List all genres available in the Books table
 10) Find the book with the lowest stock
 11) Calculate the total revenue generated from all orders

   - Advanced Queries
 1) Retrieve the total number of books sold for each genre
 2) Find the average price of books in the "Fantasy" genre
 3) List customers who have placed at least 2 orders
 4) Find the most frequently ordered book
 5) Show the top 3 most expensive books of 'Fantasy' Genre 
 6) Retrieve the total quantity of books sold by each author
 7) List the cities where customers who spent over $30 are located
 8) Find the customer who spent the most on orders
 9) Calculate the stock remaining after fulfilling all orders
  

## 🛠️ Technologies Used
- MySQL / PostgreSQL (compatible)
- SQL queries: DDL, DML, and Joins

## 📊 Key Insights
- Total Books in Inventory: 500
- Total Customers: 496
- Revenue Generated: $75628
- Average Order Value: $159.8
- Top Genre Sales: Mystery 
- Repeat Purchase Rate: 28.02%(approx.)
- Inventory Turnover Rate: 0.22%(approx.)

## 🚀 How to Run
1. Import the SQL schema into your SQL environment
2. Run <a href="https://github.com/Harsha-Gotan/SQL_Online_Bookstore/blob/main/ONLINE_BOOKSTORE%20QUERY.sql">sql_file</a> 
3. Use provided queries to analyze the database









