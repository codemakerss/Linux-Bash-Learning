# Introduction to Writing Scripts and Command-Line Tools in Bash
  
- What are Scripts and Command-Line Tools?
    
| **Statement** | **Script**  | **CLI** |
|:-------------:|:-----------:|:-------:| 
| ephemeral     | automate    | reuse   |
| `interactive` | `run again` | `input` |
  
- Building a Bash Script
  
core components:  
1. shebang line
2. debug modes
3. statements and variables
  
```bash
## shebang line
#!/usr/bin/env bash -> for chmod + x

## we can use #!/usr/bin/bash -xv for verbose debugging and shows every execution processes behind the complie
variable="one"
echo "statement $variable"
```
  
exmaple of basic bash scripts:
```bash
# Set strict mode. Causes shell to exit when a command fails
set -e

# Enables printing of shell input lines as they are read
set -v

# Enables print of command traces before executing command
set -x

# Set a variable
variable="one"

echo "This is a script with a variable: $variable"
```
  
- Building a Bash Function  
---Function-----Work--------------Final-----------  
IN ----------> Machine ----------> OUT (no return?)  
  
```bash
#!/usr/bin/env bash

## Basic structure
#function_name () {
#   command
#}

# Parameters
mimic() {
    echo "First Parameter: $1"
    echo "Second Parameter: $2"
}

# Call the function with two parameters
mimic 1 2

# Call the function again with two different parameters
mimic 99 100

# Add function
# No return value, so must echo
add() {
    num1=$1
    num2=$2
    result=$((num1 + num2))
    echo $result
}

# will echo three in this testcase
add 1 2

# capture output of function
# will echo 14 in this testcase
output=$(add 5 9)
echo $output

# add again 
add $output $output
```
  
- Building a Bash Command-Line Tool
  
./cli.sh --count 5 --phrase "hi"  
name of the script with option  
1. we need to build the function
2. we need something to parse the input
3. we need to pass input to the function
  
```bash
# generate phrase "N" times
phrase_generator() {
    for ((i=0; i<$1;i++)); do
        echo "$2"
    done
}

# parse options
while [[ $# -gt 1 ]]
do 
key="$1"

case $key in 
    -c|--count)
    COUNT="$2"
    shift 
    ;;
    -p|--phrase)
    PHRASE="$2"
    shift
    ;;
esac
shift
done

# run program
phrase_generator "${COUNT}" "${PHRASE}"
```
  
- Bash-Adjacent Tools: Makefiles and Dockerfiles
  
difference between makefile and dockerfile
| **MakeFile**  | **DockerFile** |  
|:-------------:|:--------------:|
| Automates     | Automates      |
| Recipe        | Containers     | 
| Bash like     | Format         | 
  
MakeFile example:
```Makefile
hello:
    echo "This is a recipe called hello"

goodbye:
    echo "This is a recipe called goodbye"

all: hello goodbye
```
  
DockerFile exmaple:
```docker
FROM python:3.10.1-bullseye

RUN pip install --upgrade pip\
    && pip install pandas\
    && pip install ipython
```


