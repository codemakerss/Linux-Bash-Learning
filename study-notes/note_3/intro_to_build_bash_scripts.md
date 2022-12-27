# Build Bash Scripts
  
## Introduction to Shell Logic and Contril Flow
- What is Shell Control Flow?  
if -> elif -> else
  
- Using Shell Control Flow to Solve Problems in Bash
if-else.sh
```bash 
#!/bin/sh
echo "What food do you choose? "
read FOOD

if [ "$FOOD" = "Apple" ]; then
    echo "Eat Yogurt with your Apple"
elif [ "$FOOD" = "Milk" ]; then
    echo "Eat Cereal with your Milk."
else
    echo "Eat your ${FOOD}" by itself!"
fi
```
```bash
chmod +x if-else.sh
./if-else.sh
```
  
- Using Shell Loops in Bash 
   
loopy.sh
```bash
#!/usr/bin/env bash
declare -a array=("apple" "pear" "cherry")

## now loop through the above array 
for i in "${array[@]}"
do 
    echo "This ${i}" is delicious!"
done
```
  
add-loop.sh
```bash
#!/usr/bin/env bash
echo "How Many Loops Do You Want?"
read loops

COUNT=1
while [ $COUNT -le $LOOPS ]
do 
    echo "Loop# $COUNT "
    ((COUNT++))
done
```
```bash
#!/usr/bin/env bash

for fruit in apple banana pear orange;
do echo "I love eating healthy snacks like this $fruit";done

for filename in file{1..11};do
    echo "Filename: $filename" > $filename.txt
done 
```
  
- Evaluating Conditions in Bash  
and - &&  
or - ||
  
