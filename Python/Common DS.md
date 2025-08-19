
# List
```python
l = list()
```

| syntax         | use                                 |
| -------------- | ----------------------------------- |
| `del l[index]` | Delete element using index.         |
| `del l[a:b]`   | Deleting slices. Incluisivity: `[)` |

## Snippets

Sorting list of lists based upon length of sublists:
```python
a.sort(key=len)
```

----
# Queue
## `collection.deque`

```python
from collections import deque

q = deque(["item"])
```

| syntax         | use                                          |
| -------------- | -------------------------------------------- |
| `q.popleft()`  | Pops leftmost item. Equivalent to FIFO POP.  |
| `q.popright()` | Pops rightmost item. Equivalent to LIFO POP. |
| `q.append()`   | Append to right. Equivalent to FIFO PUSH.    |

----
# Sets

```python
s = set()
```

| syntax                      | use                                                   |
| --------------------------- | ----------------------------------------------------- |
| `s.add(x)`                  | Add an element.                                       |
| `s.update([a,b,c,d,...])`   | Add multiple elements.                                |
| `s = s1.union(s2, s3, ...)` | Union.                                                |
| `x = s.pop()`               | Removes a random element from the set and returns it. |

----
# Dict
```python
d = {}
```

| syntax     | use                                 |
| ---------- | ----------------------------------- |
| `d.pop(k)` | Remove key value pair with key `k`. |

## snippets
Sort by value:
```python
d = dict()
sorted_by_value = {
		k:v for k,v in sorted(
			d.items(), key=lambda x: x[1], reverse = False
		)
}
```
