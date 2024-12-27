| Exit Status | Meaning                    |
| ----------- | -------------------------- |
| `0`         | Successfully executed.     |
| `1`         | Not successfully executed. |

Testing conditions:
| Syntax | Purpose |
|--|--|
| `test expression` | Evaluating expression. Check exit status. |
| `[ expression ]` | Evaluating expression. Check exit status. Space around `[`,`]`. |

[Operators has another dedicated file](Operators.md)

----
## if-elif-else
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

----
## case
```
case $VARIABLE in
	match_1) commands
		;;
	match_n) 
		commands
		;;
	*) commands_to_execute_by_default;;
esac
```


----
## for loop
Syntax-I:
```
for ((initialization; condition; expr))
do
	commands
done
```
- - `initialization`: is executed just for first iteration.
- `condition`: to break the loop.
- `expr`: some expression.
- All 3 above are optional. `for ((;;))` is valid.

Syntax-II:
```
for variable in sequence/range
do
	commands
done
```

----
## while
```
while [ condition ]
do
	commands
done
```
- `[ 0 ]` does not evaluate to false.
