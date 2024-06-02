# [Human Traffic of Stadium](https://leetcode.com/problems/human-traffic-of-stadium/description/)

```sql
WITH newResult AS (
    SELECT 
        s.id AS id,
        s.visit_date AS visit_date,
        s.people AS people,
        (
        IFNULL((SELECT MIN(t.id) FROM Stadium t WHERE s.id <= t.id AND t.people < 100),(SELECT COUNT(*)+1 FROM Stadium))
        - 
        IFNULL((SELECT MAX(t2.id) FROM Stadium t2 WHERE s.id >= t2.id AND t2.people < 100),0)
        ) AS 'DIFF'
    FROM Stadium s
)
SELECT
    id,
    visit_date,
    people
FROM
    newResult
WHERE 
    DIFF >= 4
```