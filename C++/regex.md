Header:
```cpp
include <regex>
```

Usage:
```cpp
# defining regex pattern
regex pattern("\\(-*\\)");

# defining iterator that iterates over the matches
sregex_iterator first(s.begin*(), s.end(), pattern);
sregex_iterator last;

# looping over the matches
for(auto itr=first; itr != last; ++itr){
	smatch match = *itr;
	int starting_index = match.position(0);
	string matched_substring = match.str();
	int length = match.length()
}

```