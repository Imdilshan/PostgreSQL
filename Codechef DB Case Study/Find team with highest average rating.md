## Link: [https://www.codechef.com/practice/course/sql-case-studies-topic-wise/SQLPRAC06/problems/SQLP60?tab=statement]

## Approach
-
-

## Properties used
-
-
```sql
-- your code goes here

select
    t.name as team_name,
    ts.user_count,
    ts.avg_rating as highest_avg_rating
from(
    select
        team_id,
        Round(AVG(rating), 2) as avg_rating,
        count(*) as user_count
    from users
    where team_id is not null
    group by team_id
) ts
join teams t on ts.team_id = t.team_id
where ts.avg_rating = (
    select max(rounded_avg)
    from(
        select round(avg(rating), 2) as rounded_avg
        from users
        where team_id is not null
        group by team_id
    ) sub
);
```

```sql 
select
    t.name as team_name,
    count(*) as user_count,
    round(avg(u.rating), 2) as highest_avg_rating
from users u
join teams t on u.team_id = t.team_id
group by t.team_id, t.name
having avg(u.rating) = (
    select max(team_avg)
    from (
        select avg(rating) as team_avg
        from users
        where team_id is not null
        group by team_id
    ) as team_averages
);
```

```sql
SELECT T.name AS team_name, COUNT(U.user_name) AS user_count, ROUND(AVG(U.rating),2) AS highest_avg_rating
FROM Teams T
JOIN Users U ON T.team_id = U.team_id
GROUP BY T.team_id, T.name
HAVING AVG(U.rating) = (
    SELECT MAX(avg_rating)
    FROM (
        SELECT AVG(rating) AS avg_rating
        FROM Users
        GROUP BY team_id
    ) AS subquery
);
```
