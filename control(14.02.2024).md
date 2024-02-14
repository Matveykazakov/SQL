# SQL

## Task - 1  
```sql
SELECT 
    SUM(o.quantity * p.price) AS total_spent,
    c.first_name,
    c.last_name
FROM Orders o
JOIN Customers c ON o.customer_id = c.customer_id
JOIN Products p ON o.product_id = p.product_id
WHERE o.order_date >= current_date - interval '1 month'
GROUP BY c.customer_id
ORDER BY total_spent DESC
LIMIT 3;
```
![image](https://github.com/Matveykazakov/SQL/assets/112616583/5e9107f7-ceb8-4247-8b3d-29d78f21c9ee)

## Task - 3  
![image](https://github.com/Matveykazakov/SQL/assets/112616583/7a4107d3-938e-46b8-86ec-314069af49e9)

```sql
UPDATE products 
SET price = price * 0.9
WHERE category = 'Clothing'
```
![image](https://github.com/Matveykazakov/SQL/assets/112616583/a4261656-009c-4927-9e6b-be190ad698eb)
Обновился 
![image](https://github.com/Matveykazakov/SQL/assets/112616583/f0f610cb-ae10-4f8b-aedb-5179717d3bfe)


## Task - 4  
```sql
SELECT category, AVG(price) AS high_price FROM Products
GROUP BY category
ORDER BY high_price DESC
LIMIT 1;
```
![image](https://github.com/Matveykazakov/SQL/assets/112616583/192aebbe-55bf-44cc-b965-daaff0787826)

```sql
SELECT category, AVG(price) AS low_price FROM Products
GROUP BY category
ORDER BY low_price 
LIMIT 1;
```
![image](https://github.com/Matveykazakov/SQL/assets/112616583/a60fd57e-a0d2-4f62-a9fb-b71cbaa3be01)

## Task - 5  
```sql
DELETE FROM orders
WHERE quantity > (
    SELECT AVG(quantity) FROM orders
);
```
![image](https://github.com/Matveykazakov/SQL/assets/112616583/a4216d0e-a2da-4f70-b6d6-cf3fcffefaa4)



