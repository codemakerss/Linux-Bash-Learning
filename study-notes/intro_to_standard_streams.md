# Introduction to Standard Streams
`using standard in / standard out / standard error`
  
## What are Standard Streams?
unix streams diagram:
input (| grep) -> errors (/Dev/null) -> outpur (filter | process)
  
## Using Standard Out
- sort & uniq
```bash
echo -e "Apple\nCarrot\nBanana"

Apple
Carrot
Banana 
```
even we can sort in orders
```bash
echo -e "Apple\nCarrot\nBanana" | sort 

Apple
Banana 
Carrot
```
we can also count for unqiue data
```bash
echo -e "Apple\nCarrot\nBanana\nApple" | sort | uniq -c

2 Apple
1 Banana 
1 Carrot
```
  
- grep
```bash
echo -e "Apple\nCarrot\nBanana\nApple" | sort | uniq -c | grep Apple

2 Apple
```  
we can check for certain process
```bash
ps -ef | grep python
```
  
- rev
```bash
echo 1993

1993

echo 1993 | rev

3991
```
  
# Using Standard In
- ask for user input 
```bash
read -p 'File: ' FILENAME

file: fruit.txt

echo $FILENAME

fruit.txt
```
we can also create a .sh file
```bash
read -p 'File: ' FILENAME
FPATH='readlink -f $FILENAME'
echo 'Full path: ' $FPATH
```
  
# Using Standard Error
- create error
```bash 
ls -l /var/FAKEDIR

ls: cannot access '/var/FAKEDIR': No such file or directory
```
  
- write error to a file
we store erros in error.txt
```bash 
ls -l /var/FAKEDIR 2>error.txt
ls -l /var/FAKEDIR 2>>error.txt (append errors)
```
  
- throw error away
```bash 
ls -l /var/FAKEDIR 2>/dev/null
```




