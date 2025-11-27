# SQL_Online_Bookstore
SQL database for an online bookstore with schema, queries and KPIs.
**Project type:** SQL / Database project  
**Description:** A relational database for an online bookstore that stores information about books, customers, and orders. The schema enforces referential integrity and supports common e-commerce queries.

## Files
- `Books.csv` - book_id (PK), title, author, price, stock, publisher, category
- `Customers.csv` - customer_id (PK), name, email, phone, address, city, state, zip
- `Orders.csv` - order_id (PK), order_date, customer_id (FK -> Customers.customer_id), book_id (FK -> Books.book_id), quantity, total_price, status

## ER Diagram
See `ER_diagram.png` for a visual representation of the entities and relationships.

## SQL Examples
1. Create tables (example for SQLite / MySQL syntax):
```sql
CREATE TABLE Books (
  book_id INTEGER PRIMARY KEY,
  title TEXT NOT NULL,
  author TEXT,
  price DECIMAL(10,2),
  stock INTEGER,
  publisher TEXT,
  category TEXT
);

CREATE TABLE Customers (
  customer_id INTEGER PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT UNIQUE,
  phone TEXT,
  address TEXT,
  city TEXT,
  state TEXT,
  zip TEXT
);

CREATE TABLE Orders (
  order_id INTEGER PRIMARY KEY,
  order_date DATE,
  customer_id INTEGER,
  book_id INTEGER,
  quantity INTEGER,
  total_price DECIMAL(10,2),
  status TEXT,
  FOREIGN KEY (customer_id) REFERENCES Customers(customer_id),
  FOREIGN KEY (book_id) REFERENCES Books(book_id)
);
```

2. Sample query — list all orders with customer name and book title:
```sql
SELECT o.order_id, o.order_date, c.name AS customer, b.title AS book, o.quantity, o.total_price
FROM Orders o
JOIN Customers c ON o.customer_id = c.customer_id
JOIN Books b ON o.book_id = b.book_id
ORDER BY o.order_date DESC;
```

3. Inventory check (books with low stock):
```sql
SELECT book_id, title, stock FROM Books WHERE stock < 5;
```

## How to run / test locally
1. If you have CSV files, import them into your SQL engine (SQLite example using sqlite3 CLI):
```bash
sqlite3 bookstore.db
.mode csv
.import Books.csv Books
.import Customers.csv Customers
.import Orders.csv Orders
```
2. Run the example queries above.

## How to upload this project to GitHub
See `UPLOAD_INSTRUCTIONS.md` (also included below) for step-by-step instructions.

---

## Notes
- Adjust data types and constraints according to your target DBMS (MySQL, PostgreSQL, SQLite).
- If orders can contain multiple books, consider splitting `Orders` into `Orders` and `OrderItems` where `OrderItems` lists book_id and quantity per order.
