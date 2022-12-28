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
```bash
# some examples to use xargs

# create some files
touch /tmp/foo{0..10}.txt
ls -l /tmp

# find files 
find /tmp -name foo* -type f -print

# perform actions after finding files
find /tmp -name foo* -type f -print | xargs /bin/rm -f
# all files removed
```
  
- Using mdfind on OS X
```bash
man mdfind

# search readme.txt only in current path and below
mdfind -name readme.txt -onlyin .
# this can auto detect new file added without using updatedb

# we can also check the files updated in realtime
mdfind -name readme.txt -onlyin . -live

# we can also customize in searching by date ranges
mdfind -name readme.txt -onlyin . data:12/1/2011-12/1/2021

# we can also look for files by certain sizes
mdfind 'kMDItemFSSize >= 10000000000'
mdfind 'kMDItemFSSize >= 10000000000' | grep Xcode | xargs du -sh
```
