[Click to go to Conditional Statements](./Conditional%20Statements.md)

## Logical operators
| Syntax | Operator |
|--|--|
| `[ $cond1 ] && [ $cond2 ]` | Logical AND |
| `[ $cond1 -a $cond2 ]` | Logical AND |
| ` [ $cond1 ]` &#124;&#124; `[ $cond2 ]` | Logical OR |
| `[ $cond1 -o $cond2 ]` | Logical OR |
| `! expression` | Logical NOT |
| `[ ! expression ]` | Logical NOT |


## Mathematical operators
| Syntax | Operator |
|--|--|
| `[ $a -eq $b ]` | Equality |
| `[ $a -ne $b ]` | Not equal |
| `[ $a -lt $b ]` | Less than |
| `[ $a -le $b ]` | Less than or equal to |
| `[ $a -gt $b ]` | Greater than |
| `[ $a -ge $b ]` | Greater than or equal to |


## Operators for strings
| Operator Syntax | Purpose |
|--|--|
| `"str1" == "str2"` | Equal |
| `"str1" != "str2"` | Unequal |

## Special operators for `test` and `[ ]`:
| Syntax | Purpose |
|--|--|
| `[ -z "someString" ]` | Unary operator. True if the string length is 0. |
| `[ -f "filePath' " ]` | Unary operator. Checks if `filePath` exists, and if the file is a regular file. |
| `[ -s "filePath" ]` | Checks if empty. |
| `[ -w "filepath" ]` | Check if write permission exists. |
| `[ $file1 -nt $file2 ]` | Checks if `$file1` is newer than `$file2` |
| `[ $file1 -ot $file2 ]` | Checks if `$file1` is older than `$file2` |
 - Regular files: Files that contains user data - text, image, audio,etc. Folders not counted.
