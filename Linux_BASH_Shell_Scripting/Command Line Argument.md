Command Line Arguments are anything that follows command or program invocation.
| Variable | Argument |
| -- | -- |
| $0 | Script file Name |
| $n | n'th argument passed to script (empty if not provided)|
| ${n} | When n>9 use curly bracketes |
| $# | Total number of arguments passed (counts from 1) |
| \`$\*\` | All arguments as a single parameter; backtick imp |
| \`$@\` | All arguments as separate parameters; backtick imp |
- $* and $@ are same without backticks.
