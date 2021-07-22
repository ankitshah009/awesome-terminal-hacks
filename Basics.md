## Link to basic posts for terminal commands 

[20 Sysadmin Linux commands](https://opensource.com/article/17/7/20-sysadmin-commands)

[A-Z of Linux Commands](https://ss64.com/bash/)

[90 frequently used sysadmin commands](https://haydenjames.io/90-linux-commands-frequently-used-by-linux-sysadmins/)

[37 important Linux Commands you should know](https://www.howtogeek.com/412055/37-important-linux-commands-you-should-know/)

[Top tips to work faster on linux and productivity or programmers and developers](https://medium.com/javarevisited/top-10-unix-and-linux-productivity-tips-for-programmers-and-developers-c748129cf3e8)

[Top 50 linux commands to know](https://www.journaldev.com/34067/linux-commands)

[100 essential linux commands](https://linuxhint.com/100_essential_linux_commands/)

### Create a password protected AES256 zip file on Macbook
Prerequisites
```
brew update && brew install p7zip
```
Command
```
7za a -tzip '-pYOURPASSWORDHERE' -mem=AES256 filename.zip files
```
