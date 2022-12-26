# Introduction to Configuring Shell Environment
  
## What are Shell Configuration Files?
~/.bashrc 
config file == automation 
- alias -> shortcuts
- source -> environment (such as python env)
- functions -> custom code 
  
## Configuring .bashrc
Github Codespaces / Azure Cloudshell / AWS Cloudshell / Google Cloudshell

Create some alias 
```bash 
## Alias
alias srcCode="cd ~/src"
```

Use apikeys more easily 
```bash
touch apiKeys.sh
```
```bash
export SECRET_ONE="123"
export SECRET_TWO="ABC"
```
then we can export path on shell
```bash 
export pathToAPIkeys="/home/cloudshell-user/apiKeys.sh"
echo pathToAPIkeys 
pathToAPIkeys
echo $pathToAPIkeys
/home/cloudshell-user/apiKeys.sh
```
then we have to configure the .bashrc
```bash
vim ~/.bashrc 

## PATH
export pathToAPIkeys="/home/cloudshell-user/apiKeys.sh"
## Source API Keys 
echo "I am sourcing this path": $pathtoAPIKeys
source $pathtoAPIKeys
```
after sourcing the ~/.bashrc
```bash
echo $SECRET_ONE
```
we have 
```bash
123
```

Python virtual environment set up
```bash 
python3 -m venv ~/.venv
source ~/.venv/bin/activate
```
then go to .bashrc 
```
## Sourcing Python Virtual ENV
echo "I am sourcing a Python Virtual ENV"
source ~/.venv/bin/activate
```
if you check which python, we have
```bash
~/.venv/bin/python
```
  
## Configuring .bashrc
using on-my-zsh with plugins 

```zsh
mdfind *.txt
```



