```sql
-- Question 1 --
SELECT
	C.ContactName,
	O.OrderID
FROM dbo.Customers AS C
JOIN dbo.Orders AS O ON C.CustomerID = O.CustomerID;
GO
```
<img width="288" height="372" alt="image" src="https://github.com/user-attachments/assets/38691e4c-e336-43bc-8bc6-9cd02595990a" />

```sql
-- Question 2 --
SELECT
	C.ContactName,
	O.OrderID
FROM dbo.Customers AS C
LEFT JOIN dbo.Orders AS O ON C.CustomerID = O.CustomerID;
GO
```
<img width="283" height="364" alt="image" src="https://github.com/user-attachments/assets/a27b7cff-c33a-4878-b86b-7d8a33a8c8c8" />

```sql
-- Question 3 --
SELECT
	C.ContactName,
	O.OrderID
FROM dbo.Customers AS C
LEFT JOIN dbo.Orders AS O ON C.CustomerID = O.CustomerID
WHERE O.CustomerID IS NULL
GO
```
<img width="269" height="338" alt="image" src="https://github.com/user-attachments/assets/dce230ac-a610-49e4-9d0d-b49a442a1ba1" />

```sql
-- Question 4 --
SELECT 
	C.CategoryName,
	P.ProductName
FROM Products AS P
JOIN dbo.Categories AS C ON P.CategoryID = C.CategoryID
GO
```
<img width="368" height="286" alt="image" src="https://github.com/user-attachments/assets/ba4c0c9c-940f-4654-a558-d4dfad2ab8bc" />

```sql
-- Question 5 --
SELECT 
	P.ProductName,
	S.CompanyName,
  C.CategoryName
FROM Products AS P
JOIN dbo.Categories AS C ON P.CategoryID = C.CategoryID
JOIN dbo.Suppliers AS S ON P.SupplierID = S.SupplierID
GO
```
<img width="652" height="307" alt="image" src="https://github.com/user-attachments/assets/0df66c61-2320-423e-8e5c-767e2985e01f" />

```sql
-- Question 6 --
SELECT 
	O.OrderID,
	O.ProductID,
	P.ProductName
FROM dbo.[Order Details] AS O
JOIN dbo.Products AS P ON O.ProductID = P.ProductID
GO
```
<img width="399" height="336" alt="image" src="https://github.com/user-attachments/assets/20c2d2dc-fb17-4a47-9963-d817921cfdee" />
