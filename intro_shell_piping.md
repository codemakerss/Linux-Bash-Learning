# Introduction to Shell Piping 
`series of tubes`
## What is shell piping?
**Input -> Process -> Out**
Example: Linux Pipes
        ------> | ------> | ------>
        ls-h      wc-l      > out.txt
process 1         2         3

## Examples
conditions for command:
ls -l README.md && touch newfile.txt
(if the ls -l file conditions meet then it will execute the
touch command for newfile.txt)

processing lines with pipelines:
```bash
STR=$'1. This is a line\n2. This is line\n3. This is a line.'
```
```bash
echo "$STR"
```
```bash
@codemakerss ➜ /workspaces/Linux-Bash-Learning (main ✗) $ echo "$STR"
1. This is a line
2. This is line
3. This is a line.
```
or even we can store lines in .txt file 
```bash
echo "$STR" > lines.txt
```
or we can sort lines file and use less if it is a bigger 
file 
```bash
cat lines.txt | sort -r | less
```
or we can only extract the line that we want from files
and output to another file 
```bash
cat lines.txt |  grep 3 > matchline.txt
```

if we want to append some lines for a file 
```bash
echo "something" > append.txt
echo "another thing" >> append.txt (appending lines after)
```

concept of throwing away errors
instead of see this below 
```bash
ls -l /wrong/path
ls: cannot access '/wrong/path': No such file or directory
```
we will throw away the standard errors 
```bash
ls -l /wrong/path 2> /dev/null
```

check to see the data streams such as logs
```bash
tail -f /var/log/dpkg.log (tail -f will keep the file open and we can see the data change everytime when there are new outputs generated)
```
only show last/head two lines or number of lines 
```bash
tail -n 2 /var/log/dpkg.log
head -n 2 /var/log/dpkg.log
```



## Shorcuts for shell commanding 
control + a - goes to the front of shell command
control + e - goes to the end of shell command