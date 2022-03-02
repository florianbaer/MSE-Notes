---
id: 3qkegx4d6ewiusgycyhc7ph
title: Cte
desc: ''
updated: 1646230416535
created: 1646228736218
---
# Common Table Expressions

CTE can be used with recursive clause to deal with hierarchical or tree structured data.
``` sql
WITH movies_etp AS (
SELECT * from movies WHERE name ilike ‘P%’
),
--tmp2 AS (
--…
--)
SELECT * from movies_etp ORDER BY name;

```

for recursive calls:
```sql
WITH RECURSIVE query_name [ (column_name [,...]) ] AS (
-- non-recursive term
SELECT …
UNION ALL
-- recursive term
SELECT …
)
SELECT ...;
```

A datatype defines possible values - e.g. Int = integer numbers but defines as well how data is stored and indexed.
Contains as well constructors, operators, functions and optimizers (with index extensions)

