
## Creating
```shell
# Creating files
cat "content" > file.txt  # create a file with content
touch <filename> # Create an empty file

# Creating directories
mkdir <dirname>  # Create a directory
mkdir dir1/dir2  # Create directory and if needed parent too
```

## Moving and Renaming
```
# moving; also used for renaming
mv <move-from-path>/tomove <move-to-path>/
# if destination has same name entity, then its overwritten.
```

## Searching
```
# find: finding files
find <location-to-find-in> -name <name> -type f -size +10k -size -20k -exec ls -al {} + 2>/dev/null
```

## File descriptors
> **File descriptors** are non-negative integers that represents an open. It is used by OS to manage and perform operations on that resource.

Standard file descriptors:
- `0`: STDIN - Standard Input
- `1`: STDOUT - Standard Output
- `2`: STDERR - Standard Error

Usage:
```shell
# redirecting stdout
find / -name *.sh > output.txt
find / -name *.sh 1>output.txt

# redirecting stderr to /dev/null
find / -name *.sh 2>/dev/null

# redirecting stderr and stdout to different files
find / -name *.sh 2>errors.txt 1>./output.txt
find / -name *.sh 2>errors.txt > output.txt

# Redirecting stdin
cat < input.txt
```

Append and streaming:
```shell
# redirect STDOUT and append to a file
find / -name *.sh >> output.txt
# redirecting STDIN to a file
cat << EOF > streamed.txt
# will run till EOF is provided
```

## Pipes
Used to redirect STDOUT and useful when STDOUT of one program is to be used as STDIN for another.  
Usage:
```shell
# get list of files | count the lines
ls -l | wc -l
```

## Reading files
```shell
cat file       # Print content of file on the terminal                  |
tail -n 5 file # Print last 5 lines of file on the terminal             |
tail -f file   # Print last few lines and update any new lines written.

grep "pattern" # Match the given pattern in given text
grep -A 5 -B 6 ... # show 5 lines before matching sentence and 6 lines after
grep -A 7 ... # Also show 7 lines before and after matching sentence
```