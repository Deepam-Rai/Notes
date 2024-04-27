
# operations

| operation           | use           |
| ------------------- | ------------- |
| `std::stoi(string)` | String to int |
|                     |               |

----
# functions

| function                                    | use                                                                                                   |
| ------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| `.substr(starting_index, length_of_substr)` | Substring of string. If length is not given then till the end is taken.                               |
| `.find_first_not_of(const string& str)`     | Returns index to first element not in given string. If no such character then returns `string::npos`. |
|                                             |                                                                                                       |

----
# Code snippets

Splitting the string:
```cpp
std::string s = "ab.cd.ef";
std::stringstream ss(s);
std::string segement;
while(std::getline( ss, segment, '.')){
	cout<<" "<<segment;
}
```
