# Fix Slow Queries

## Use explain analyze
```
 explain analyze
 select * from post order by view_count desc limit(10)
```
