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



