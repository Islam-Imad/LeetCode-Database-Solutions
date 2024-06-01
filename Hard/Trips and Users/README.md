# [Trips and Users](https://leetcode.com/problems/trips-and-users/description/)

```sql
WITH Trip AS(
    SELECT *
    FROM Trips
    WHERE NOT EXISTS (SELECT banned FROM Users WHERE users_id IN (driver_id, client_id) and banned='Yes') AND request_at BETWEEN "2013-10-01" AND "2013-10-03"
)
SELECT
    a.request_at AS 'Day',
    ROUND(
        (
            SELECT COUNT(b.id)
            FROM Trip b
            WHERE b.status != 'completed' and b.request_at = a.request_at
        )
        /
        (
            SELECT COUNT(b.id)
            FROM Trip b
            WHERE b.request_at = a.request_at
        )
        ,2
    ) AS 'Cancellation Rate'

FROM Trip a
Group by a.request_at
```