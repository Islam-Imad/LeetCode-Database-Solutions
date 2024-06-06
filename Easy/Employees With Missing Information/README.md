# [Employees With Missing Information](https://leetcode.com/problems/employees-with-missing-information/description/)

```sql
WITH Result AS (
    SELECT 
        Employees.employee_id
    FROM 
        Employees
    WHERE 
        Employees.employee_id NOT IN (SELECT Salaries.employee_id FROM Salaries)
    UNION
    SELECT 
        Salaries.employee_id
    FROM 
        Salaries
    WHERE 
        Salaries.employee_id NOT IN (SELECT Employees.employee_id FROM Employees)
)
SELECT * FROM Result ORDER BY employee_id
```