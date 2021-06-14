# awesome-terminal-hacks
A repository consisting of useful commands required in daily tasks to reduce stackoverflow searches. 

## Task 

```
Find the list of all extensions in a folder and subdirectories. 

Command : find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u
```

```
Find the list of all extensions in a folder and its subdirectories with counts 

Command : find . -type f | sed -e 's/.*\.//' | sed -e 's/.*\///' | sort | uniq -c | sort -rn
```
