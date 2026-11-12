## Link: [https://www.codechef.com/practice/course/sql-case-studies-topic-wise/SQLPRAC06/problems/SQLP56]

## Approach
-
-

## Properties used
-
-
```sql
-- your code goes here

select sum(rating) as pro_peoples
from users
where pro_plan = 1;

```

```sql
-- your code goes here

select sum(case when pro_plan =1 then rating else 0 end) as pro_peoples
from users;
```
