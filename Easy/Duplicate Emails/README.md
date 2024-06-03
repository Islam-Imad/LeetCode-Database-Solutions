# [Duplicate Emails](https://leetcode.com/problems/duplicate-emails/description/)

```sql
SELECT email
FROM Person
GROUP BY email
HAVING count(email) > 1
```