# Introduction to Manipulating Data in the Bash Shell
  
- Shell Techniques for Data in the Bash Shell  
1. Truncate : head 10 / tail 10 / -n 3  
```bash
#!/usr/bin/env bash

echo "How Many Lines Do You Want?"
read LINES

COUNT=1
while [ $COUNT -le $LINES ]
do
    echo "COUNT $RANDOM" >> file.txt
    ((COUNT++))
done
## we can use head or tail to only look at small amount of data in a file
## we can also use shuf -n 3 file.txt to randomly pick three data from a file
```
  
2. Filter : grep "bird" / cut (column)
```bash
#!/usr/bin/env bash

# Randomly generates a string in lines
echo "How Many Lines Do You Want?"
read LINES

declare -a array={"apple" "pear" "cherry"}

COUNT=1
while [ $COUNT -le $LINES ]
do
    rand =$[ $RANDOM % 3 ]
    echo "COUNT ${array[$rand]}" >> filter-file.txt
    ((COUNT++))
done

# Find pattern 
grep apple filter-file.txt

# Count occurrences 
grep -c apple filter-file.txt

# Find either pattern
grep -e apple -e pear filter-file.txt

# Count occurrences of both patterns 
grep -c -e apple -e pear filter-file.txt

# Show all lines that DO NOT contain pattern
grep -v apple filter-file.txt
```
  
3. Search find / locate
```bash 
## Find files

# Find all bash scripts - dot means the current path 
find . -name "*.sh"

# Find all CSV files
find . -name "*csv"

# Find all executable non-invisible files - perm /+x means executable file  
find . -perm /+x ! -name '.*' -type f

# Find all executable non-invisible files and ignore .git directories
find . -perm /+x -not -path '*/\.*' -type f
```

