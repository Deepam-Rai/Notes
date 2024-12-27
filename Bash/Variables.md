# Variables
- Temporary storage.
- Exists for the lifespan of the program/terminal session.

## Types: System variables and User Defined Variables

| System Variables | User Defined Variables |
|--|--|
| Created and Maintained by BASH Shell | Created and Maintained by users|
| All Uppercase | Adviced to avoid all uppercase format|
| eg: BASH_VERSION, HOME, etc | Any userdefined variables|


# Global and Local Variables (in a shell)
- Global variables: Defined outside function.
- Local variables: Defined inside function.
- By default all variables are global.
- Inside function local variable has higher priority than global variable.
- The global variables set in script remains persistent after the script ends, until the session is terminated.



| Command | Use |
|--|--|
| set | Display all set Variables and Functions|
| printenv | Display all set Variables |
| echo "$VARIABLE_NAME" | Show Variable value |
|\<variable>=\<value> | Set a new variable; Changing the value of set variable |
| unset \<variable> | Unset a set variable |
| read -p "\<text prompt>" \<variable> | Prompt a text message; take input; save to the variable. [[Input Output#Accepting user inputs via keyboard]]|
| \<variable>=\`\<command>\` | Saving output of a command to a variable |

# `export` command
- Create child shell by running `/bin/bash`
| Command | Purpose |
|--|--|
|`export <myvar>=<value>` | Now we can use this variable globally in all child shells too. |
