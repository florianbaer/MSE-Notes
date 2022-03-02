---
id: uhemofj34vg8jafd2877yk6
title: Arraytypes
desc: ''
updated: 1646231691841
created: 1646230869345
---

# Array types
- Arrays are a sort of collections
- They have a fixed or variable size
  
In pg - any datatype can be stored as array and are **index 1 based**!

```sql
CREATE TABLE sal_emp ( 
    name text, 
    pay_by_quarter integer[], 
    schedule text[][]  -- two dimensional array
);


INSERT INTO sal_emp VALUES (
'Bill', 
ARRAY[10000, 10000, 10000, 10000], 
ARRAY[['meeting', 'lunch'], 
['training', 'presentation']]
); 

-- Works as well
SELECT ARRAY[1,2,3+4]; 
-- returns an array with values {1,2,7}


-- equal: =
SELECT ARRAY[1,3] = ARRAY[1,3];
SELECT ARRAY[1.1,2.1,3.1]::int[] = ARRAY[1,2,3];
SELECT ARRAY[3,1] = ARRAY[1,3]; -- !!
-- is contained by: <@
SELECT ARRAY[3,1] <@ ARRAY[1,3]; -- !! 
SELECT ARRAY[2,7] <@ ARRAY[1,7,4,2,6];
-- overlap - have at least one element in common: &&
SELECT ARRAY[1,4,3] && ARRAY[2,1];
-- ANY syntax
SELECT * FROM sal_emp
WHERE 30000 = ANY (pay_by_quarter); 


--- is the value 3 and 77 and 1 in the array 3,1,4
SELECT ARRAY[3,77,1] <@ ARRAY[3,1,4];
-- will output false!

```


