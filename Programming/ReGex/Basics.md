>**ReGex or Regular Expressions:** are sequence of characters that specifies a match pattern in a text.

## Grouping
Allows groupings of patterns.  

| Opeartor | Description                                                       |
| -------- | ----------------------------------------------------------------- |
| `(a)`    | The patterns within the parenthesis should be processed together. |

## Wildcards

| Wildcard | Matches                      |
| -------- | ---------------------------- |
| `.`      | Any character except newline |
| \|       | OR operator                  |
| `^`      | Start of a string            |
| `$`      | End of a string              |
| `\`      | Escape special characters    |

## Quantifiers

| Quantifier | Matches                                          |
| ---------- | ------------------------------------------------ |
| `*`        | 0 or more of previous pattern                    |
| `+`        | 1 or more of the previous pattern                |
| `?`        | 0 or 1 of the previous pattern                   |
| `{5}`      | Exactly 5 of previous pattern                    |
| `{5,}`     | 5 or more occurrences of previous pattern        |
| `{5-10}`   | Occurrences between 5 and 10 of previous pattern |

## Character Classes

| Classes        | Matches                                                                      |
| -------------- | ---------------------------------------------------------------------------- |
| `[xyz]`        | Any of the enclosed characters                                               |
| `[a-zA-Z0-9]`  | Any of the character in the range                                            |
| `[^xyzA-F]`    | Negation: Anything that is not enclosed in the square brackets               |
| `[0-4[6-8]]`   | Union of character classes                                                   |
| `[0-9&&[345]]` | Intersection of character classes                                            |
| `[0-9[^345]]`  | Subtraction in character classes                                             |
| `.`            | Any single characters except line terminators                                |
| `\d`           | Any digit. `[0-9]`                                                           |
| `\D`           | Any character that is not a digit. `[^0-9]`                                  |
| `\w`           | Any alphanumeric character including underscore. `[a-zA-Z0-9_]`              |
| `\W`           | Any character that is not alphanumeric including underscore. `[^A-Za-z0-9_]` |
| `\s`           | Single whitespace character                                                  |
| `\S`           | Any single character that is not whitespace                                  |
| `\t`           | Horizontal tab                                                               |
| `\r`           | Carriage return                                                              |
| `\n`           | Linefeed                                                                     |
| `\v`           | Vertical tab                                                                 |
| `\f`           | Formfeed                                                                     |
| `\b`           | Backspace and also word-boundary (start/end of a word) assertion             |
