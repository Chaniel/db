# Performance of PostgreSQL

## Add pg_stat_statements Extension, monitor each query.

### Create pg_stat_statements
```
CREATE EXTENSION pg_stat_statements;
```
### Edit Config File postgresql.conf
```
# file: postgresql.conf
shared_preload_libraries = 'pg_stat_statements'

```

### Restart pg Server
```
select * from pg_stat_statements;

```


## Show Query's Execution Time

```
SELECT 
  (total_time / 1000 / 60) as total_minutes, 
  (total_time/calls) as average_time, 
  query 
FROM pg_stat_statements 
WHERE query NOT LIKE '%pgbench%' and query NOT LIKE 'BEGIN;%' and query NOT LIKE 'END;%'
ORDER BY 1 DESC 
LIMIT 100;
```
## Create Index 
```
create index concurrently posts_view_count_idx on posts(view_count);

# if use `create index`, table will be locked. so you should use `create index concurrently`
```
## Resources
- www.westnet.com
- http://pgtune.leopard.in.ua/
- www.craigkerstiens.com
- http://www.craigkerstiens.com/2013/01/10/more-on-postgres-performance/

## Conclusion

- the size of db more big, more hits on disk IO.

