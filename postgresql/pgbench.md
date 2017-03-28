
## Read Test(select)

### Start Bench
```
 createdb bench
 pgbench -i -s 100 bench
 pgbench -j 1 -T 10 -S -c 5 bench

```

### Result
```
starting vacuum...end.
transaction type: SELECT only
scaling factor: 100
query mode: simple
number of clients: 5
number of threads: 1
duration: 10 s
number of transactions actually processed: 64545
latency average: 0.776 ms
tps = 6444.144260 (including connections establishing)
tps = 6445.917776 (excluding connections establishing)

```


## Resources
www.westnet.com
http://pgtune.leopard.in.ua/

## Conclusion
```
the size of db more big, more hits on disk IO.
```
