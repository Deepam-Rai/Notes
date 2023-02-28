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
| `${#arr[n]}` | n'th element (index starts at 0)|
| `${arr[@]` | Whole array |
| `${#arr[n]` | Length of n'th element |
| `${!arr[@]` | Accesing array indices(`!`) |
| `${arr[@]:a:b}` | Extract `b` elements starting from offset `a`; `a` inclusive|
| `${arr[n]:a:b` | Extract `b` elements with offset `a`(inclusive) of `n`'th element |
| `${arr[@]/a/b/}` | **Replace** `a`(regex accepted) with `b` in `arr` and return |
| `unset arr[n]` | **Remove** `n`'th element of array |
| `newarr="${arr[@]}"` | **Copy** |
| `newarr=("${arr1[@]}" "${arr2[@]}")` | **Concatenation** |
| `unset arr` | **Deletion** |

- No spaces around `=`

- Bash allows array operations on variables, which arent declared as arrays too.