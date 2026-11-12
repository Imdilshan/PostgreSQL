## Link: [https://www.codechef.com/practice/course/sql-case-studies-topic-wise/SQLPRAC06/problems/SQLP58?tab=statement]

## Approach
-
-

## Properties used
-
-
```sql
-- your code goes here
select u.college, u.user_name
from users u
join (
    select college, max(rating) as max_rating
    from users
    group by college
) t on u.college=t.college and u.rating = t.max_rating;
```

```sql
-- your code goes here
select u.college, u.user_name
from users u
join (
    select college, max(rating) as max_rating
    from users
    group by college
) t on u.college=t.college and u.rating = t.max_rating;
```

```sql 
-- your code goes here
select college, user_name
from users u1
where rating = (
    select max(rating)
    from users u2
    where u2.college = u1.college
);
```

```sql
SELECT college, user_name
FROM Users
WHERE (college, rating) IN (
  SELECT college, MAX(rating)
  FROM Users
  GROUP BY college
);
```
