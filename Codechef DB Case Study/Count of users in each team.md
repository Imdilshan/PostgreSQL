## Link: [https://www.codechef.com/practice/course/sql-case-studies-topic-wise/SQLPRAC06/problems/SQLP57]

## Approach
-
-

## Properties used
-
-
```sql
-- your code goes here

select t.name as team_name, count(*) as user_count
from users u
join teams t 
    on u.team_id = t.team_id
group by t.team_id
order by t.name;
```

```sql
SELECT t.name AS team_name,
       u.user_count
FROM Teams t
JOIN (
    SELECT team_id, COUNT(*) AS user_count
    FROM Users
    GROUP BY team_id
) u ON t.team_id = u.team_id
WHERE u.user_count > 0
ORDER BY t.name;
```
