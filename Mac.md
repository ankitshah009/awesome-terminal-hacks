### Enable performance mode in MacOS
```
sudo nvram boot-args="serverperfmode=1 $(nvram boot-args 2>/dev/null | cut -f 2-)"
sudo reboot
```
Note - if you want to know what this command does -- run sysctl -a before running this command and after running the same command. 
Reference - https://support.apple.com/en-us/HT202528
