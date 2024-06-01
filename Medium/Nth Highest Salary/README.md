# [Nth Highest Salary](https://leetcode.com/problems/nth-highest-salary/description/)

```sql
CREATE FUNCTION getNthHighestSalary(N INT) RETURNS INT
BEGIN
  RETURN (
       WITH maxn AS (SELECT salary , DENSE_RANK() OVER (ORDER BY salary DESC) AS rRank FROM Employee)
       SELECT salary
       FROM maxn
       WHERE rRank = N
       LIMIT 1
  );
END
```