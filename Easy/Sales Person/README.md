# [Sales Person](https://leetcode.com/problems/sales-person/description/)

```sql
WITH RED AS (
    SELECT sales_id
    FROM Orders
    INNER JOIN Company ON name = "RED" AND Company.com_id = Orders.com_id
)
SELECT name
FROM SalesPerson 
WHERE sales_id NOT IN (SELECT * FROM RED)
```