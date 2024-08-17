---
title: python funkyness
date created: 2024-08-16T16:42  
date modified: 2024-08-16T16:42 
tags:
- software
- python
---


Python has some funky stuff, this are some details that I might need in the future, once I forget it

## deleting items while iterating on itself

You can't, have to do it in a second stage:

```python
item_list = [item for item in item_list if <positive-condition>]

```
