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

#### Perform operation on all files in a path -- example here is to remove _ from filenames
```
for FILENAME in *; do FILENAME1=${FILENAME#*_}; mv $FILENAME $FILENAME1; done 
```
Note - this above for loop can be used to do many stuff accordingly. Useful to have this in mind

#### Swap columns in a file - can be modified as per your needs
```
awk 'BEGIN{FS=OFS=","}{$0=$2 FS $2 FS $1}1' <your comma delimited file>
```
Note - read awk documentation to perform lots of crazy commmands based on the above template. Learn awk - its very useful nifty tool and no installation needed on any Linux OS. 

#### Copy fastest using tar
```
tar cf - * | mbuffer -m 1024M | ssh user@host '(cd /home/path; tar xf -)'
```

#### Extract wav audio files form an mp4 extension of video - crude way - more customization is possible. 
```
for f in *.mp4;do ffmpeg -i "$f" "${f%mp4}wav";done
```

#### Replace spaces with underscores -- very irritating to handle spaces in filenames -- easy tool to fix that so your code doesnt need to handle. 
```
for file in */*; do echo $file; mv "$file" $(echo $file | sed 's/ /_/g'); done
```

#### Quickly get sum of a file consisting of numbers 
```
awk 'BEGIN {FS=" "};{sum+=$NF} END {print sum}' <your file>
```

#### Common lines between 2 files in Linux
```
comm -12 <(sort file1) <(sort file2)
```
```
grep -Fxf file1 file2
```
both grep and comm has same execution time roughly for relatively small txt files less than 50mb. Post that grep is better for larger files. 

#### Get Lines unique to file1 in linux
```
comm -23 <(sort file1) <(sort file2)
```

#### Get lines unique to file2 in linux
```
comm -13 <(sort file1) <(sort file2)
```
Ignore case in comm command by passing comm -i 

#### Get unique lines in your file (sort if not sorted)
```
sort file1 | uniq 
```

#### Get number of times unique lines appear in a file (sort if not sorted)
```
sort file1 | uniq -c 
```

#### Only print the repeated lines once in a file. (sort if not sorted) (basically count > 1 lines)
```
sort file1 | uniq -d 
```

#### Only print the lines which are not repeated in a file. (sort if not sorted) (basically count == 1 lines)
```
sort file1 | uniq -u
```

# Note
If you know a better way to do the tasks - create a pull request for the repository. 

Many of the commands here are created as per my needs and can be easily modified to ones suited task. 

Kindly star the repository/share it if this helps reduce your time to make searches/helps in your work. 
