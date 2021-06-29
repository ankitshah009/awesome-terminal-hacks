### List users current job and the commands being run
```
for jobid in `squeue -u $USER | awk '{print $1}' | grep -v JOBID`; do echo $jobid `scontrol show jobid -dd $jobid | grep Command`;done
```
