- unique elements
- immutable elements: can add or remove elements but cannot change them
- Elements are sorted according to the comparison function of the set. We can provide this comparison function during declaration.
# Usage
Header
```cpp
#include <set>
```

Declaration:
```cpp
// std::set<data_type> s;
// std::set<data_type, comparision_fun()> s;
```

Initialization:
```cpp
set<int> s = {1,2,3,5};
```

----
# Operations

| Operation          | Use                 |
| ------------------ | ------------------- |
| `.insert(element)` | Insertion           |
| `.erase(element)`  | Deletion            |
| `.clear()`         | Delete all elements |
|                    |                     |
|                    |                     |

----
# Methods

| Function         | Use                                                                |
| ---------------- | ------------------------------------------------------------------ |
| `.empty()`       | `True/1` if empty                                                  |
| `.size()`        | Returns number of elements                                         |
| `.find(element)` | If present returns the iterator to the element else `.end()`       |
| `.begin()`       | Iterator to the first element in the set.                          |
| `.end()`         | Returns iterator to the element after the last element of the set. |

----
# Snippets

Set diference:
```cpp
#include<algorithm>

set<char> setS(s.begin(), s.end()), setT(t.begin(), t.end()), setDiff;
// setDiff = setT - setS
set_difference(
	setT.begin(), setT.end(),
	setS.begin(), setS.end(),
	inserter(setDiff, setDiff.begin())
);
```

