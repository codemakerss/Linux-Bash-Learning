# Introduction to Working with Shell Variables
  
## What are shell variables and how to use them
a way of storing data that you use in another script or another process
Example:
```bash
export Food="apple"
echo [$Food]
echo "I Love" $Food
```  
## Exporting shell variables in an interactive prompt 
- Parent / Child shell variables (global variables)
first shell:
```bash
export var=1
echo $var
```
child shell access still works 
```bash
echo $var
```
- No child shell access (local variables)
```bash
var=1
```  
## Using shell variables in a Bash Script
source - after making changes and is at the current shell
we could have some alias proj&& source env.sh to get certain projects to run  
  
script - almost child shell 
./runENV.sh but have no access to variables in parent shell 
