# [Rank Scores](https://leetcode.com/problems/rank-scores/description/)

```sql
SELECT
    score
    ,ROW_NUMBER() OVER (
        ORDER BY score DESC
    )AS 'rank'
FROM
    Scores
```