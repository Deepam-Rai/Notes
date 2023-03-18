| Exit Status | Meaning |
|--|--|
| `0` | Successfully executed. |
| `1` | Not successfully executed. |

| Syntax | Purpose |
|--|--|
| `test expression` | Evaluating expression. Check exit status. |
| `[ expression ]` | Evaluating expression. Check exit status. Space around `[`,`]`. |

Special operators for `test` and `[ ]`:
| Syntax | Purpose |
|--|--|
| `[ -z "someString" ]` | Unary operator. True if the string length is 0. |
| `[ -f "filePath' " ]` | Unary operator. Checks if `filePath` exists, and if the file is a regular file. |
- Regular files: Files that contains user data - text, image, audio,etc. Folders not counted.

[Operators has another dedicated file](Operators.md)

## `if-elif-else-fi`
```bash
if [ expression ]; then
	commands
elif [ expression ]; then
	commands
else
	commands
fi
```

- quote string variables if used in conditions.