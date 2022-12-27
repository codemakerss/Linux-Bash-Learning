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