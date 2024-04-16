
# Usage

Declaration:
```cpp
std::unordered_set<data_type> name;
```

Initialization:
```cpp
// from vectors
std::unordered_set<data_type> name(vec.begin(), vec.end())
```

----
# Operations

| Operations         | use       |
| ------------------ | --------- |
| `.insert(element)` | Insertion |
|                    |           |

----
# methods

| function         | use                                                     |
| ---------------- | ------------------------------------------------------- |
| `.size()`        | Returns number of elements                              |
| `.empty()`       | Returns true if set is empty                            |
| `.find(element)` | Returns iterator if element found else returns `.end()` |
| `.begin()`       | Returns iterator to                                     |

----
# iterator

```cpp
std::unordered_set<data_type>::iterator itr;
```
