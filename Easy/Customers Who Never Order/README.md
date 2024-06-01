# [Customers Who Never Order](https://leetcode.com/problems/customers-who-never-order/description/)

```sql
SELECT name AS 'Customers'
FROM Customers
WHERE NOT EXISTS (SELECT * FROM Orders WHERE Orders.customerId = Customers.id)
```