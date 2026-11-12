## Link: [https://www.codechef.com/practice/course/sql-case-studies-topic-wise/SQLPRAC06/problems/SQLP55]

## Approach
-
-

## Properties used
-
-
```sql
-- your code goes here

select round(100.0 * sum(case when rating >= 2200 then 1 else 0 end)/count(*), 2) as percentage
from users;
```
