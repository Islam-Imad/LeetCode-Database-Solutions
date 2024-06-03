# [Tree Node](https://leetcode.com/problems/tree-node/description/)

```sql
SELECT 
    t1.id,
    CASE 
        WHEN (t1.p_id IS NULL) THEN "Root"
        WHEN (EXISTS (SELECT t2.id FROM Tree t2 WHERE t2.p_id = t1.id)) THEN "Inner"
        ELSE "Leaf"
    END AS type
FROM Tree t1
```