# argparse

```python
import argparse  
  
parser = argparse.ArgumentParser("arg_parser")  
parser.add_argument("-my_flag", help="Help message for my_flag", type=str)  
args = parser.parse_args()  
my_flag = args.my_flag
print(f"my_flag value = {my_flag}")
```

Usage:
```shell
python script.py -my_flag "value"
```
