# json parsing
```
import json

text = '''
{
	"Name" : "value",         # taken as string
	"Name2" : 23,             #taken as int
	"nested" : {              #nesting allowed
		"name1" : 12,
		"listAlso" : [1,2,3]  #taken as list
	}                         #comma not allowed for last element
}
'''
text = text.replace("'","\"") #needs double quote

parsed = json.loads(text)

print(parsed["nested"]["listAlso"][0] + 20)  #accessing
```

| Command | Use |
| -- | -- |
| `json.dump()` |  |
| `json.dumps()` | |
| `json.load()` | JSON object in a file to Python dictionary |
| `json.loads(jsonString)` | JSON string to Python dictionary |
