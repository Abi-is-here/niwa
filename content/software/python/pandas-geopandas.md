---
title: Pandas library
date created: 2024-08-16T16:40  
date modified: 2024-08-16T16:40 
tags:
- software
- python
---

## installation

```pip install pandas geopandas```

## snippets

### add a column that depends on another one:

```python
df = df.assign(id=fp["_id"]["$oid"])

```

### reset index

```python
dataframe.reset_index(drop=True,inplace=True)
```

useful when doing concats, as it doesn't reset the index column each time and duplicates appear

### Get random sample

```python
dataframe.sample(10)
```
