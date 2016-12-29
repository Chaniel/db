### dump
```
#  -O, --no-owner               skip restoration of object ownership in
#  -x, --no-privileges          do not dump privileges (grant/revoke)
pg_dump -O -x   site-list_development > /tmp/site-list.sql
```


### dump db
```
bin/pg_dump -h 127.0.0.1 -p 5432 -O -x db_name > db_name.sql
```

### dump sites(table) in db_name(db)
```
bin/pg_dump -h 127.0.0.1 -p 5432 -O -x -t sites db_name > sites.sql
```

### restore db use pg_restore
```
pg_restore -d osdba osdba.dump
```

### restore table use psql
```
bin/psql -h 127.0.0.1 -p 5432 -d db_name < sites.sql
```
