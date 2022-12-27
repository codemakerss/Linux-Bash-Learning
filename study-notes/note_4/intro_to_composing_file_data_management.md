# Introduction to Composing File and Data Management Solutions in Linux
  
## Introduction to Searching a Filesystem in Linux
- Methods for Searching a Filesystem in Linux  
Visual method -> foo.txt -> dir  
Live methond -> look at subset of data, etc 
Metadata Search methond -> locate .txt
  
- Using the Locate Command to Find Files in Linux
```bash
# install mlocate
sudo yum install mlocate 

# if E: Package 'mlocate' has no installation candidate
sudo apt update
sudo apt install mlocate

# manually update file database and remember to updatedb if new file added
sudo updatedb

# find all paths for .zshrc
locate .zshrc

# count how many times .zshrc file exists
locate -c .zshrc
```
  
- Using the Find Command to Find Files in Linux
```bash
# find current path file 
find . -name .zshrc

# find all files in all paths 
sudo find / -name .zshrc

# one thing to note is that find command is much more expensive and took more time compared to locate command 
```
  
- Using xargs to Extend Search Capabilities in Linux
