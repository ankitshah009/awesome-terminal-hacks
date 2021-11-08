### Enable performance mode in MacOS
```
sudo nvram boot-args="serverperfmode=1 $(nvram boot-args 2>/dev/null | cut -f 2-)"
sudo reboot
```
Note - if you want to know what this command does -- run sysctl -a before running this command and after running the same command. 
Reference - https://support.apple.com/en-us/HT202528


### Spotlight indexing issues --> mds stores causing CPU 100% 
https://apple.stackexchange.com/questions/144474/mds-and-mds-stores-constantly-consuming-cpu
```
Monitor using 

sudo fs_usage -w -f filesys mds_stores
```
Add the filesystem not required to the Spotlight remove indexing
