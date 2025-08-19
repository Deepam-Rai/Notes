----
# Creating `requirements.txt`

All packages in current environment:
```shell
pip freeze > requirements.txt
```
Only the used packages:
```shell
pip install pipreqs
pipreqs .
```

----

# Command line arguments

## Using `sys.argv`

```python
import sys

len(sys.argv)  # Total arguments passed
sys.argv[i]    # i'th argument passed, zero-indexing
python_script = sys.argv[0]  # 0'th argument is always script-name
int(sys.argv[i])  # received as str by default. typecast required
```
