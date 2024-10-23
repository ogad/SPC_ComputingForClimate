< [Visual Studio Code](./2_1_VisualStudioCode.md) | [SSH and SCP](./3_2_SSH.md) >

# Remote computing
Doing your work somewhere with more power and space.

## Why do remote computing?
The resources on your machine will leave you unable to do some parts of your work.
Maybe you'll need too much data in storage, need to load too much into memory, it would take too long on the computing power you have, or you need to analyse data securely stored elsewhere.
Essentially when you either have one "big job" to do, or you have to do lots and lots of small jobs (or the same job on lots of separate data!)

High performance computing (what we call "supercomputers") involves chaining together lots of separate computers into one big system, which lots of users can use at once.
Each computer in the system is called a node.
You can often connect to the system (via a "login node") and view/interact with the file system.
Resource-intensive jobs should never be run on the login nodes—they slow down the system for everyone else.
For these jobs you should reserve resources using the batch system (or use a dedicated node for certain types of work on machines where they're provided).
The most important thing is to read the documentation for the system you're using and follow their instructions.

## Interactive computing
Some remote computers are reasonably small in scale and you are allowed to directly access them and use them in the same way you would use your own computer.
You can connect via SSH (giving you a terminal).
VS Code also has a remote development extension (it also connects via ssh, then installs some software in your remote home directory, and you can connect your local instance to the remote instance).
The VS code remote developent extension is really useful—but only use it on resources you're allowed to (e.g. don't use it on the Imperial HPC login node).
The "Spat computers" are great when you need just a bit more power, space to store/access stored data, or don't want to choke up your own computer.
Different groups use different resources, so speak to your supervisor about this if you haven't already.

Cloud computing "boxes" can also enable a similar connection and are widely used in industry, but aren't common in academia yet—but the skills you're developing are well suited to apply to this.

Some HPC systems let you use their resources similarly to you would use your own computer.
They do this via Jupyter notebook servers, by reserving some resources using the batch system.
Jasmin and the Imperial HPC support both these methods of interactive computing.

## The module system
Lots of hpc systems run a module system (which avoids users having to install all their own applications).
You'll have to load relevant modules (including e.g. [anaconda for python on the Imperial HPC](https://icl-rcs-user-guide.readthedocs.io/en/latest/hpc/applications/guides/conda), or [Jaspy on jasmin](https://help.jasmin.ac.uk/docs/software-on-jasmin/jaspy-envs/)) you should be able to find documentation for the relevant system.

## The batch system
When you've written some code to run on the hpc, you can submit it using the batch system.
You have to write a job script—a shell script to run the code and prescribe the resources you need.

Different batch systems exist. The ones I've seen are `slurm` and `pbs`—they're similar but have some differences.
The Imperial HPC uses `pbs`, but Jasmin uses `slurm`.

When you specify a job you need to include the job specification at the top of the job script.
This needs to include:
1. The walltime - the maximum time to run each job.
2. The number of cores (and sometimes the number of different *nodes*)
3. The amount of memory

A basic `pbs` job script guide is found at the [Imperial Research Computing Service User Guide](https://icl-rcs-user-guide.readthedocs.io/en/latest/hpc/getting-started/running-your-first-job/), and for `slurm` on the [Jasmin help site](https://help.jasmin.ac.uk/docs/batch-computing/slurm-quick-reference/).

## Parallelisation and array jobs
Often, you have to run a similar analysis over e.g. lots of different timesteps in different files.
You can submit this kind of work as an **array job**.
This is the simplest way to parallelise your code (especially when you're using a batch system).

You specify the "array indices" to run the job over as part of the array specification.
Again, the RCS has [details for pbs](https://icl-rcs-user-guide.readthedocs.io/en/latest/hpc/queues/array-jobs/) and the [Jasmin help site for slurm](https://help.jasmin.ac.uk/docs/batch-computing/how-to-submit-a-job/#job-array-submission).

This can submit lots of jobs (each of which is allocated the specified resources—**memory and cores are usually per array index, not for the whole job**).
The job index is then stored in an environment variable (`$PBS_ARRAY_INDEX` or `$SLURM_ARRAY_TASK_ID`), which can be passed to the python script, for example:
```bash
python my_script.py $PBS_ARRAY_INDEX
```
and then read in the python script:
```python
import sys
index = int(sys.argv[1])
```

## What resources are available to me?
- [The Imperial HPC and RCS](https://icl-rcs-user-guide.readthedocs.io/en/latest/) - Imperial's centralised HPC (after registering with the RCS).
- [Jasmin](https://jasmin.ac.uk/about/) - funded by NERC for climate data analysis with direct access to CEDA data archives (requires registering and approval).



## Sources
- [Imperial Research Computing Service User Guide](https://icl-rcs-user-guide.readthedocs.io/en/latest/)
- [Spat computing guide](http://www.sp.ph.ic.ac.uk/computing/)
- [Jasmin Help site](https://help.jasmin.ac.uk/)

< [Visual Studio Code](./2_1_VisualStudioCode.md) | [SSH and SCP](./3_2_SSH.md) >
