# Back Up

## Back Up and Compress

### 1. use pipe and gzip
```
pg_dump -d db_name | gzip > db_name_bak.gz
```

### 2. use pg_dump -c
```
pg_dump -Fc db_name > db_name.bak
pg_restore -d db_name db_name.bak
```
