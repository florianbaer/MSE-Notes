---
id: 8pzvuh0fyuhmlhzbih4qz8b
title: Key-Value Stores
desc: ''
updated: 1646834395729
created: 1646829588641
---
# Key value stores
[[mse.ss22.sw03]]

One way of usig it in postgres is `hstore`

```sql
--enable exteinos
create extension hstore

-- delete extension 
drop extension hstore

-- usage
select 'a=>x, b=>y'::hstore -> 'a' -- is an extension delivered with postgres-contrib
```

Dictionary is an abstract data structure which contains a value or several values.

Key values pairs are used to make a schema-less / schema-later / open schema model.

- **Possibly suitable for**
  - Easy data storage and data capture
  - Rows with many attributes that are rarely examined
  - Semi-structured data
- **Tips**
  - Try to avoid reporting against big heaps of Dictionaries
  - Consider additional attributes with lookup keys (see Free Text Search)
  - Consider running triggers or a post-process to transform KVPs into an entity-based schema.



```sql
select 'a => 1, a=>2'::hstore; -- only saves the first occurance 
-- "a" => "1", so value 2 is ignored

select akeys('key3=>3, key2=>2'::hstore)
-- [key3, key2]

select 1 as id, each('key3=>3, key2=>2'::hstore) -- returns tuples

select each(kykvpfield) from ... -- returns all kvp as tuples
```

# PostGIS

```sql
select *, tags->'tourism' as featureclass
from osm_location where tags->'tourism' in ('camp_site','caravan_site');
-- find camping sites on https://terminal.osmdatapipeline.geoh.infs.ch/
```

# Tree

A tree is a graph without cycles

- Parent / Child / Ancestor Nodes
- Sibling Nodes
- Root Node: Only Node which does’nt have a parent
- Leaf Node: Node which has no child
- Internal Node: Node which is neither the root nor the leaf node
- Level of a Node (depth)
- Degree of a Node: No. of children a node has
- Height of Tree: Max. level of nodes in that tree
- Subtree of a Tree

**Postgres even has Ltree**

![Tree Data Structures](/assets/images/2022-03-09-14-44-39.png)

# JSON
PostgreSQL knows JSON and JSONB
- JSON: Textual storage «as is», multiple keys
- JSONB: Internal binary, one key, indexable

**use jsonb_pretty() for printing**

Accessors: ->, ->> #>, #>>
Processing: @>

```sql
select '{"a":1, "b":2, "c":3}'::jsonb @> '{"c":3, "b":2}'::jsonb
-- returns ture
```



