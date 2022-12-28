# Introduction to Modifying Files, Directories, Permissions and Archiving in Linux
  
- Overview of Modifying the Filesystem in Linux
  
based on records  
| **Database**  | **Filesystem** |  
|:--------------|:-------------------:|
| C - create    | touch, mkdir        |
| R - read      | cat, less, grep     | 
| U - update    | mv, tar, zip, chmod | 
| D - delete    | rm, rmdir           | 
  
- Moving Files and Directories in Linux
```bash 
# dir - dir - dir : )
mkdir -p bar/bam/biz

# synchronizing dirs 
rsync -av foo/ newspot/foo/
# this will update foo dir files to be exactly the same as foo dir
```
  
- Setting Permissions on Files and Directories in Linux
  
![permission_file](https://github.com/codemakerss/Linux-Bash-Learning/blob/main/study-notes/note_4/permission_pic.png)