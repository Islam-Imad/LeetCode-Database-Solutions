# [Sales Analysis III](https://leetcode.com/problems/sales-analysis-iii/description/)

```sql
SELECT 
    product_id,
    product_name
FROM
    Product
WHERE
    NOT EXISTS (
            SELECT * 
            FROM Sales 
            WHERE Sales.product_id = Product.product_id AND sale_date NOT BETWEEN '2019-01-01' AND '2019-03-31'
            )
    AND EXISTS (
            SELECT * 
            FROM Sales 
            WHERE Sales.product_id = Product.product_id AND sale_date BETWEEN '2019-01-01' AND '2019-03-31'
            )
```