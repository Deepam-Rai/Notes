# Types
3 types
| Type | Quote | Purpose |
| -- | -- | -- |
| double quotes | "" | Substitutes values of variables and commands within |
| single quotes | '' | Turn off special meaning of all characters |
| backslash | \\ | Escapes a character; removes special meaning from a character |

Example:
| Command | Output |
|-|-|
|`echo "user $USER"` | `user <username>` |
| `echo 'user $USER'` | `user $USER` |
| `echo "user \$USER"` | `user $USER` |


