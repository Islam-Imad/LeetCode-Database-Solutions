# [Find Total Time Spent by Each Employee](https://leetcode.com/problems/find-total-time-spent-by-each-employee/)

```sql
SELECT
    event_day AS 'day',
    emp_id,
    SUM(out_time) - SUM(in_time) AS total_time
FROM
    Employees 
GROUP BY event_day , emp_id
```