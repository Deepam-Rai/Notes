
- Used to store similar datatypes.
- Can grow dynamically.
- Part of Standard Template Library(STL).

----
# Usage

Header file:
```cpp
#include <vector>
```

Declaration:
```cpp
std::vector<int> vec;
```

Initialization:  
```cpp
// Initializer list
std::vector<int> vec = {1, 2, 3, 4, 5};

// uniform initializatoin
std::vector<int> vec{1, 2, 3, 4, 5};

// constructor initialization
std::vector<int> vec(5, 7);
// is equivalent to: std::vector<int> arr = {7, 7, 7, 7, 7}
```

---
# Operations

| Operations   | Reserve         |
| ------------ | --------------- |
| `.reserve()` | reserving space |


| Operations                                                                      | Use                                                             |
| ------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| `.push_back (value);`                                                           | Add element at end                                              |
| `.insert (iterator position, const value_type& val);`                           | Insert single value                                             |
| `.insert (const_iterator position, size_type n, const value_type& val)`         | Insert same value repeatedly                                    |
| `.insert (iterator position, InputIterator first, InputIterator last)`          | Input range                                                     |
| `.insert (iterator position, initializer_list<value_type> il)`                  | Using initializer list                                          |
| `.emplace( const_iterator pos, Args&&... args );`                               | Insertion                                                       |
| `.at(index)`                                                                    | Accessing element                                               |
| `vec[index]`                                                                    | Accessing element                                               |
| `.at(index) = <new value>`                                                      | Assigning value                                                 |
| `.pop_back()`                                                                   | Remove last element                                             |
| `.clear()`                                                                      | Remove all elements                                             |
| `.erase(iterator position)`                                                     | Deletion from specified position                                |
| `.erase(starting_pos, ending_pos)`                                              | Deletion in range                                               |
| `std::merge(vec1.begin(), vec1.end(),vec2.begin(), vec2.end(), merged.begin())` | Merging vectors                                                 |
| `std::find(vec.begin(), vec.end(), elementToFind)`                              | Finding elements. Returns the iterator if present else `.end()` |
|                                                                                 |                                                                 |

- `insert()` needs to shift the elements if new element is not in extreme ends of vector. This causes performance issues.
- When reallocation takes place, all references to elements reallocated are invalidated.
- `.at()` throws exception for out of bound error while `[]` gives garbage value.
- 

----
# vector methods

| function                              | Use                                                                              |
| ------------------------------------- | -------------------------------------------------------------------------------- |
| `.size()`                             | Returns number of elements of vector                                             |
| `.capacity()`                         | Returns the overall size of the vector                                           |
| `.clear()`                            | Removes all elements of the vector                                               |
| `.front()`                            | Returns the first element                                                        |
| `.back()`                             | Returns the last element                                                         |
| `.empty()`                            | Returns `(True)` if the vector is empty                                          |
| `.begin()`                            | Returns iterator to the first element                                            |
| `.end()`                              | Returns iterator to the theoretical element that comes after last element        |
| `.rbegin()`                           | Returns reverse iterator pointing to last elements and iterates backwards.       |
| `.rend()`                             | Returns reverse iterator pointing to first element and iterates forwards.        |
| `std::unique(vec.begin(), vec.end())` | Bring all duplicates to the end and returns the iterator where duplicates begin. |
|                                       |                                                                                  |

----
# Vector iterators
- used to point to the memory address of vector element.

Declaration:
```cpp
// iterator for int vector
vector<int>::iterator iter;
```

Initializatoin:
```cpp
iter = arr.begin();     // point to first element
iter = arr.begin() + 1; // point to the second element
iter = arr.end() - 1;   // point to last element
```

Accessing vector value from iterator:
```cpp
value = *iter; // dereferencing the iterator
```

----

# Code snippets

Removing duplicates:
```cpp
// using unique and erase
sort(vec.begin(), vec.end());
auto it = unique(vec.begin(), vec.end());
vec.erase(it, vec.end());
```

```cpp
// converting to set
unordered_set<data_type> temp_s; // may need to create a hashFunction
for(auto item: vec)
	temp_s.insert(item);
vec.assign(temp_s.begin(), temp_s.end());
```
