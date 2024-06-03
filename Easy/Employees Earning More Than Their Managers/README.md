# [Employees Earning More Than Their Managers](https://leetcode.com/problems/employees-earning-more-than-their-managers/description/)

```sql
SELECT 
    A.name AS 'Employee'
FROM
    Employee A
WHERE EXISTS (SELECT B.id FROM Employee B WHERE B.id = A.managerId AND A.salary > B.salary)
```