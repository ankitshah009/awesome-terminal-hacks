### List users current job and the commands being run
```
for jobid in `squeue -u $USER | awk '{print $1}' | grep -v JOBID`; do echo $jobid `scontrol show jobid -dd $jobid | grep Command`;done
```

### See the list of Available GPUs on the cluster
```
sinfo -o "%20P %5D %3c %6m %G" | grep -v null
```

### List all the Nodes including GRES 
```
scontrol show nodes
```

### Get information with specific params for all nodes on cluster
```
sinfo -o "%10P %8c %8m %11G %5D %N"
```
### Cancel job ids from slurm
```
scancel jobid
```
All users jobs
```
scancel -u USER
```
Pending jobs
```
scancel -t PD
```
### See SLURM nodes features and capacity - individual output
```
sinfo -o "%20N %10c %10m  %20f  %10G" -N
```
