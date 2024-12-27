
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
```shell
# moving; also used for renaming
mv <move-from-path>/tomove <move-to-path>/
# if destination has same name entity, then its overwritten.
```

## Searching
```shell
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
cat file       # Print content of file on the terminal
head -n 5 file # Print first 5 lines
tail -n 5 file # Print last 5 lines of file on the terminal         
tail -f file   # Print last few lines and update any new lines written.
less <file>
more <file>
```


Operations on file contents:
```shell
# sort
cat <file> | sort  # sorts alphabetically

# search
cat <file> | grep "pattern" # result lines that matches pattern
... | grep "pat1\|pat2"  # multilpe patterns
... | grep -v <pattern>  # all lines that doesnt contain pattern
... | grep -A 5 -B 6 ... # show 5 lines before matching sentence and 6 lines after
... | grep -C 7 ... # Also show 7 lines before and after matching sentence

# cut
cat <file> | cut -d":" -f1  # delimit on ":" and return 1st field

# tr: translation/squeeze/delete characters
cat <file> | tr a-z b-za  # replace a-y with b-z and z with a
# note that not all encoding has contiguous assignment like ASCII

# column view
cat /etc/passwd | grep -v "false\|nologin" | replace ":" " " | column -t

# processing with awk
# show users and their shell:
cat /etc/passwd | tr ":" " " | awk '{print $1, $NF}' | column -t

# sed: stream editor: useful for replacing
cat /etc/passwd | sed 's/replaceThisPattern/withThisPattern/g'

# wc: counting
cat /etc/passwd | wc -l  # count the lines
```
- We can use RegEx with `grep -E`. Regex Section: [Programming/ReGex/README.md](../Programming/ReGex/README.md)
- 