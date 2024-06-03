# [Department Highest Salary](https://leetcode.com/problems/department-highest-salary/description/)

```sql
WITH ranked_table AS(
SELECT
    departmentId
    ,name
    ,salary
    ,RANK() OVER(
        PARTITION BY departmentId ORDER BY salary DESC
    )AS 'rank'
FROM
    Employee
)
SELECT 
    dep.name  AS Department,
    rt.name   AS Employee,
    rt.salary As Salary
FROM 
    ranked_table rt 
INNER JOIN 
    Department dep ON dep.id = rt.departmentId
WHERE rt.rank = 1
```