# [Game Play Analysis I](https://leetcode.com/problems/game-play-analysis-i/description/)

```sql
SELECT 
    player_id,
    MIN(event_date) AS 'first_login'
FROM Activity
GROUP BY player_id
```