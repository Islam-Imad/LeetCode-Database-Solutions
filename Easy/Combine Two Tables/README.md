# [Combine Two Tables](https://leetcode.com/problems/combine-two-tables/description/)

```sql
SELECT 
    P.firstName
    , P.lastName
    , Ad.city
    , Ad.state
FROM 
    Person as P
LEFT OUTER JOIN Address as Ad ON Ad.personId = P.personId
```