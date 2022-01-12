How to use a linear array on files or directories that are not linear.  For example, if you want to work through directories such as:

```

dir1/
dir5/
dir22/
dir31/
...
dir801/
dir850/
```
You could create an array that emcompasses the min and max directory numbers and then check if it exists to then run a task:

```

#SBATCH --array=1-850

[ -e dir${SLURM_ARRAY_TASK_ID} ] && mycode.py dir${SLURM_ARRAY_TASK_ID}
```
