- Values can be heterogenous.
- No max limit for size.
- Zero based indexing.
- Some may be left uninitialized

| cmd | Purpose |
|--|--|
| `declare -a <arrayname>` | **Declaration** |
| `arrayname[index]='value'` | **Initialization** |
| `declare -a arr=('e1' 'e2' 'e3')` | Declaration and Initialization |
| `arr=('e1' 'e2' 'e3')` | Declaration and initialization |
| `arr=([index]='value' [idx2]=val2)` | Index based initialization |
| `${#arr[@]}` | **Length** |
| `${arr[@]` | Whole array |
| `${#arr[n]}` | Length of n'th element |
| `${!arr[@]` | Accessing array indices(`!`) |
| `${arr[@]:position:no_of_elements}` | Extract `no_of_elements` elements starting from offset `position`(inclusive)|
| `${arr[n]:a:b}` | Extract `b` elements with offset `a` (inclusive) of `n`'th element |
| `${arr[@]/a/b/}` | **Replace** `a`(regex accepted) with `b` in `arr` and return |
| `unset arr[n]` | **Remove** `n`'th element of array |
| `newarr="${arr[@]}"` | **Copy** |
| `newarr=("${arr1[@]}" "${arr2[@]}")` | **Concatenation** |
| `arr=("${arr[@]}" "newElement")` | **Appending** to an array. |
| `unset arr` | **Deletion** |

- No spaces around `=`

- Bash allows array operations on variables, which aren't declared as arrays too.