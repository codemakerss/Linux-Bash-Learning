# Linux-Bash-Learning
This for learning linux and bash for data engineering.

## Linux Commands Notes 
cmd  -option target 

Time and Date:
* cal 
* date

Disk Usage or File Size:
* df -h
* du -sh

Exploring:
* pwd 
* ls -lah (all file information - size, datetime)
* cd /tem cd ~
* which python3

Viewing files:
* less /etc/password
* cat /etc/password

Counting lines:
* wc -l /etc/password

Modifying Files and Directories:
* touch newfile.txt
* mkdir newdir
* mv newfile.txt newdir (change file directory)
* mv newfile.txt newfile2.txt (change file name)
* mkdir -p moredir/dir1/dir2 (create multiple directory)
* rm -rf moredir

Processes:
* ps
* ./sleeper.sh 
(if a file goes infinite or want to stop the file - using control+z or if want to kill the process - using control+
z) & (you can check the stopped process - using command 
"jobs")
* ./sleeper.sh & (this will put the file in the backgroud
to execute but cannot be stopped by using control+z ro +c)
(if you want to go back to foregroud - using fg and job number then you can use control+z or +c)
* fg 1 (this is for reprocess the stopped one - using fg job number)

**Learn more from [DockerHub-Python](https://hub.docker.com/_/python)**