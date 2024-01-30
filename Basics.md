## Link to basic posts for terminal commands 

[20 Sysadmin Linux commands](https://opensource.com/article/17/7/20-sysadmin-commands)

[A-Z of Linux Commands](https://ss64.com/bash/)

[90 frequently used sysadmin commands](https://haydenjames.io/90-linux-commands-frequently-used-by-linux-sysadmins/)

[37 important Linux Commands you should know](https://www.howtogeek.com/412055/37-important-linux-commands-you-should-know/)

[Top tips to work faster on linux and productivity or programmers and developers](https://medium.com/javarevisited/top-10-unix-and-linux-productivity-tips-for-programmers-and-developers-c748129cf3e8)

[Top 50 linux commands to know](https://www.journaldev.com/34067/linux-commands)

[100 essential linux commands](https://linuxhint.com/100_essential_linux_commands/)

[Using Unix for Linguistic Research](https://wstyler.ucsd.edu/unix/)

### Create a password protected AES256 zip file on Macbook
Prerequisites
```
brew update && brew install p7zip
```
Command
```
7za a -tzip '-pYOURPASSWORDHERE' -mem=AES256 filename.zip files
```

### Get list of current active screens on account
```
#!/bin/bash
num=$1
echo $num
sessdir=`screen -ls | sed -ne 's/.*Sockets* in \(.*\)\.$/\1/p'`
newest=`ls -1t $sessdir | head -$num`
echo $newest
```

### Basic command and its information
```
grep: A powerful tool for searching text. It's used to search for a specific string or pattern within files. Example: grep 'pattern' filename.

awk: Great for text processing, especially for manipulating data in files or streams. Example: awk '{print $1}' filename prints the first column of a file.

sed: A stream editor that can perform basic text transformations on an input stream (a file or input from a pipeline). Example: sed 's/original/replacement/' filename replaces the first instance of 'original' with 'replacement' in each line of the file.

find: Helps in searching for files in a directory hierarchy. Example: find / -name filename.txt searches for a file named filename.txt starting from the root directory.

tar: Used for compressing and archiving files. Example: tar -czvf archive.tar.gz /path/to/directory creates a compressed archive of a directory.

wget: A non-interactive network downloader. Useful for downloading files from the internet. Example: wget http://example.com/file.

curl: Similar to wget, but with more features. It's used to transfer data from or to a server. Example: curl http://example.com.

ps: Displays information about running processes. Example: ps -aux shows all running processes with detailed information.

top: An interactive task manager that shows a real-time view of running processes.

alias: Creates shortcuts for long commands. Example: alias ll='ls -la' creates an alias ll for ls -la.
```
