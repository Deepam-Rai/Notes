Declaration:
```cpp
std::data_type::iterator itr;
```

----
# Operations

| function         | use                                      |
| ---------------- | ---------------------------------------- |
| `std::next(itr)` | Return the iterator to the next element. |
| `++itr;`         | Move iterator to next.                   |
- We cant perform arithmetic operations like `itr + 1` directly on iterators. Instead use `next()` etc.