# [Rearrange Products Table](https://leetcode.com/problems/rearrange-products-table/)

```sql
SELECT
    product_id,
    'store1' AS store,
    store1 AS price
FROM
    Products
WHERE
    store1 IS NOT NULL
UNION
SELECT
    product_id,
    'store2' AS store,
    store2 AS price
FROM
    Products
WHERE
    store2 IS NOT NULL
UNION
SELECT
    product_id,
    'store3',
    store3 AS price
FROM
    Products
WHERE
    store3 IS NOT NULL
```