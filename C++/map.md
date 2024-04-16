
# Map

> **map**:  container used to store indexed values.

- each value is mapped to a key
- keys are unique
- type of all values are same. but type of key and the value can be different.

----
## Usage

Header:

```cpp
#include <map>
```

Declaration:
```cpp
// map< key_type, value_type>map_name;
map<string, string> food;
```

Initialization:
```cpp
map<string, string> food = {{"apple", "fruit"}, {"potato", "vegetable"}};

// using copy constructor
map<string, string> food2(food);
```


----
## map operations

| function                    | use                 |
| --------------------------- | ------------------- |
| `.insert({"key", "value"})` | Insertion           |
| `my_map["new key"]="value"` | Assignment          |
| `.erase("key")`             | Deletion            |
| `.clear()`                  | Delete all elements |
|                             |                     |

----
## map functions

| function       | use                                                              |
| -------------- | ---------------------------------------------------------------- |
| `.begin()`     | Iterator to the first element pair                               |
| `.end()`       | Iterator to the element that follows last element(theoretically) |
| `.size()`      | Number of elements                                               |
| `.clear()`     | Clear all elements                                               |
| `.find("key")` | Returns iterator to the element if present else returns `.end()` |
|                |                                                                  |
|                |                                                                  |


----
## Common snippets
Iteration:
```cpp
for( auto element: food){
	// key = element.first;
	// value = element.second;
}
```

Checking if key exists:
```cpp
if(my_map.find("key")==my_map.end()){
	cout<<"key is not present"<<endl;
}
```

----

