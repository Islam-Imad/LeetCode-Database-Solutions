# [Bank Account Summary II](https://leetcode.com/problems/bank-account-summary-ii/description/)

```sql
SELECT
    name,
    SUM(amount) AS balance
FROM
    Users AS U
INNER JOIN
    Transactions AS T ON U.account = T.account
GROUP BY U.account
HAVING balance > 10000
```