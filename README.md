# Retail-Customers-Products-Analysis-with-SQL
Retail customer &amp; product analysis with SQL Server — mastering INNER JOIN, LEFT JOIN and Anti-Join patterns to answer real business questions.


this project is a customer & product analysis for a retail business, built with **SQL Server**.

This project focuses on one of the most essential skills for a data analyst: **working with JOINs like a pro**. In real-world databases, data is never in a single table — you need to know how to connect tables correctly, without losing or duplicating data.

---

##  Business Context

The dataset includes **customers, orders, products, product categories, and suppliers**. The goal was to answer questions like:

- What orders has each customer placed?
- Which customers haven't placed any orders yet?  
  *(In the real world, this is the foundation of marketing campaigns and win-back strategies!)*
- Which category and supplier does each product belong to?

---

##  Database Structure & Relationships

| Table | Description |
|---|---|
| `Customers` | Customer information |
| `Orders` | Orders |
| `[Order Details]` | Order line items |
| `Products` | Products |
| `Categories` | Product categories |
| `Suppliers` | Suppliers |

### Key relationships:

- Each `Order` links to one `Customer` (via `CustomerID`)
- Each `[Order Details]` row links to one `Order` and one `Product`
- Each `Product` has a `Category` and a `Supplier`

**Database ERD**

> <img width="1026" height="498" alt="image" src="https://github.com/user-attachments/assets/2410bae9-2877-477f-9f32-3f155db3b377" />


---

##  Business Questions Answered

| # | Question | Technique |
|---|---|---|
| 1 | Customers who placed orders + their order numbers? | `INNER JOIN` |
| 2 | All customers, even those with no orders? | `LEFT JOIN` |
| 3 | Customers who never placed any order? | `LEFT JOIN` + `IS NULL` |
| 4 | All products + their category? | `INNER JOIN` |
| 5 | Products + supplier company name + category? | Three-table `JOIN` |
| 6 | Orders + codes and names of related products? | `INNER JOIN` |

---

##  Skills & Techniques Used

-  `INNER JOIN` and `LEFT JOIN` — and more importantly, knowing **when** to use which
-  The **Anti-Join** pattern (`LEFT JOIN` + `WHERE ... IS NULL`) to find customers with no orders
-  **Multi-table JOINs** (connecting Products to both Categories and Suppliers simultaneously)
-  Reading an **ERD** and understanding **Primary Key / Foreign Key** relationships before writing queries
-  Clean **table aliasing** to keep queries readable

---

##  The Learning Point of This Project

Questions 1, 2, and 3 are actually **one continuous story**:

- **Question 1:** With `INNER JOIN`, only customers with orders show up.
- **Question 2:** With `LEFT JOIN`, all customers show up — even orderless ones (their `OrderID` column shows `NULL`).
- **Question 3:** Adding `WHERE O.CustomerID IS NULL` filters down to only the orderless customers.

Put together, these three demonstrate that I understand JOIN types **conceptually**, not just memorized syntax.

```sql
-- Customers who have never placed an order
SELECT
    C.ContactName,
    O.OrderID
FROM dbo.Customers AS C
LEFT JOIN dbo.Orders AS O
    ON C.CustomerID = O.CustomerID
WHERE O.CustomerID IS NULL;
```

---

##  Repository Structure

```
├── database/          # Table creation & sample data scripts
├── queries/           # Queries for questions 1-6
├── screenshots/       # Query output screenshots
└── README.md
```

---

## 📬 Contact Me

- **Data Analyst:** Mohammadhasan Pourkabgani
- **Email:** Mh.pourkabgani91@gmail.com
- **LinkedIn:** [add your link here]
- **GitHub:** [add your link here]
