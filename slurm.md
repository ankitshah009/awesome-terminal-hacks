### List users current job and the commands being run
```
for jobid in `squeue -u $USER | awk '{print $1}' | grep -v JOBID`; do echo $jobid `scontrol show jobid -dd $jobid | grep Command`;done
```

### See the list of Available GPUs on the cluster
```
sinfo -o "%20P %5D %3c %6m %G" | grep -v null
```
