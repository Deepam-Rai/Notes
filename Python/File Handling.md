# Modes
| Mode | Purpose | Overrides? | If the file doesnt exist |
| -- | -- | -- | -- |
| r | Read | - | `FileNotFoundError` |
| w | Write | Yes | Creates |
| a | Append | No(Appends) | Creates |
| r+ | Read and Write | No(Appends) | `FileNotFoundError` |
| w+| Write and Read | Yes | Creates |
| a+ | Append and Read | No(Appends) | Creates |

# Functions and usages
| Command | Purpose |
| -- | -- |
| `f = open(filename, mode)` | Open a file. |
| `f.read()` |  Read entire file as string. |
| `f.read(n)` | First `n` character of the file. |
| `f.write(<string>` | Write to the file. |
| `f.close()` | Close a file. |

# with block
Easier syntax, automatically does `close()` when the block ends.
```
with open(filename, mode) as f:
	.
	.
	for line in f:
		print(line)
	f.write()
	.
	.
```



# OS operations on file
`import os`

| Command | Purpose |
| -- | -- |
| `os.path.exists(filename)` | Check if file exists. |
| `os.remove(filename)` | Remove file. |
| `os.getcwd()` | Get current working directory. |
| `os.chdir(path)` | Change Directory. |
