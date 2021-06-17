# awesome-terminal-hacks
A repository consisting of useful commands required in daily tasks to reduce stackoverflow searches. 

Just click on the right of the codeblock to copy the command and use it directly in your work. 

## Task 

#### Find the list of all extensions in a folder and subdirectories.
``` 
find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u
```

#### Find the list of all extensions in a folder and its subdirectories with counts 
```
find . -type f | sed -e 's/.*\.//' | sed -e 's/.*\///' | sort | uniq -c | sort -rn
```

#### Find files greater than a particular size in linux
```
 find . -type f -size +4G
```

#### find files less than a particular size in Linux
```
find . -type f -size -4G
```

#### NVIDIA command - check the GPU resource usages
```
nvidia-smi && nvidia-smi pmon -c 1 | awk -F ' ' '{print $2}' | xargs -0 > t1 && export i=0; export l2="-"; while IFS='' read -r line;do if [[ "$i" -lt 2 || -z "$line" || "$line" == $l2 ]];then echo $i; else ps -p "$line" -o pid,vsz=MEMORY -o user,group=GROUP -o comm,args=ARGS | awk '{for ( x=1 ; x<=1 ; x++ ) { printf("%s\t",$x) } for (x=2;x<=2;x++) { if(NR>1) { printf("%13.2fMb\t",hr=$x/1024) } else { printf("\t%s\t",$x) } } for ( x=3 ; x<=NF ; x++ ) { printf("%s ",$x) } print "" }'; fi; i=$((i+1)) ;done < t1 && rm t1
```

#### Copy fastest using tar
```
tar cf - * | mbuffer -m 1024M | ssh user@host '(cd /home/path; tar xf -)'
```


# Note
If you know a better way to do the tasks - create a pull request for the repository. 

Kindly star the repository/share it if this helps reduce your time to make searches/helps in your work. 
