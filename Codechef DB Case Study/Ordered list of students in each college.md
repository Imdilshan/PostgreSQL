## Link: [https://www.codechef.com/practice/course/sql-case-studies-topic-wise/SQLPRAC06/problems/SQLP59]

## Approach
-
-

## Properties used
-
-
```sql
-- your code goes here

select 
    college,
    count(*) as user_count
from users
where college is not null
group by college
order by user_count asc;
```

```sql 
SELECT college, COUNT(*) AS user_count
FROM Users
GROUP BY college
HAVING college IS NOT NULL
ORDER BY user_count ASC;
```
