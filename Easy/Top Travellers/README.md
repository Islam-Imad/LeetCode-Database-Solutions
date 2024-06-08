# [Top Travellers](https://leetcode.com/problems/top-travellers/description/)

```sql
SELECT
    U.name,
    IFNULL(SUM(R.distance),0) AS travelled_distance
FROM
    Users AS U 
LEFT OUTER JOIN Rides AS R ON R.user_id = U.id
GROUP BY U.id
ORDER BY 2 DESC,1 ASC
```