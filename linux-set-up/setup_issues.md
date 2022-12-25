# Issues while config Linux

## .vimrc issue
don't mix with nvim and vim, even we make .vimrc in $HOME directory, vim could use nvim config instead. To check whether our .vimrc being used or not, try to run this below :
```bash
strace -o vim_strace vim
```
this will generate a file in the users path and we have to quit(:q) vim after executing the line. Then, we use grep to search .vimrc in vim_trace file.
```bash
cat vim_trace | grep .vimrc
```
generate results 
```bash
openat(AT_FDCWD, "/home/username/.vimrc", {st_mode=S_IFREG|3123, ...},0) = 0
```
if "=-1 ENOENT", it means no such file or directory or .vimrc not being used