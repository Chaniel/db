# Optimizing Textual Queries

## Term non SARGABLE(non Search ARGable)

this is non SARGABLE
```
select * from posts where body LIKE '%pain%'
```

this is SARGABLE
it will index posts where the body starts with word 'pain'
```
select * from posts where body LIKE 'pain%'
```

## Create Text Index

```
create index concurrently idx_body_comments on comments(text text_pattern_ops)

explain
select * from comments where text like 'pain%'
```

## Full Text Searching
```
alter table posts
add column search tsvector
select * from posts where to_tsvector(body) @@ to_tsquery('pain')


create index concurrently 
idx_search_posts on posts 
using GIST (search)

```
