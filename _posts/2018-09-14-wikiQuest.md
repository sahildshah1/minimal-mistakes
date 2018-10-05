---
published: true
title: "Getting started with NU's computing cluster"
---

Here are the notes I took when I was getting started with Northwestern's high
performance computing cluster [Quest](http://www.it.northwestern.edu/research
/user-services/quest/index.html)


## Applying for projects allocations:

-   Research Allocation I: 35000 compute hours approved on a rolling basis.
    They'll usually grant it within a day or two. You can read more about it here:
     http://www.it.northwestern.edu/research/user-services/quest/allocation-guidelines
     html

-   Genomics Nodes on Quest : Access to 100 genomics nodes each with 24 cores and 128GB
    of memory. For jobs that requiring more than 10 nodes or that run for more than 48
    hours, users must request a reservation: http://www.it.northwestern.
    edu/research/user-services/quest/genomics.html


-   Allocation applications require a statement of purpose. Example outline: 
    (1) Research question under investigation with enough background for a reader
    outside your field, (2) Description of computations you ran, (3) Results you 
    obtained, (4) Brief explanation of how these results will further the work 
    on the research problem defined  


## Logging into QUEST and checking status of projects:

-   ssh into Quest with ssh NETID@quest.it.northwestern.edu

-   To get information about your home (or project directory) (i.e. space) or check 
    the status of your project allocations: https://kb.northwestern.edu/page.
    php?id=70712



## Running jobs on Quest (using R)

-   For info on using R on Quest (including managing R packages): 
    https://kb.northwestern.edu/page.php?id=71270

-   For information about running jobs on Quest (Note: interactive job 
    still require an allocation ID):  https://kb.northwestern.edu/page.php?id=69247

1.  Clone your git repo containing your R scripts onto Quest
2.  Write a submission script specifying the resources you need and what 
    commands to run: https://kb.northwestern.edu/page.php?id=69247

3.  Submit this script to the scheduler by running an msub command on the command line.

-   Recommended that you always load a specific version of R rather than relying on
    the default version

-   If your code is not parallelized, one core on one node may be appropriate for 
    your job

-   Managing Jobs on Quest after submitted: 
    https://kb.northwestern.edu/page.php?id=70710


## Installing R package 

-   For info on using R on Quest (including managing R packages): 
    https://kb.northwestern.edu/page.php?id=71270

-   R packages are installed, whether system-wide or locally in your own 
    directory, for specific versions of R.

-   It is recommended to start R interactively from a login node to install 
    packages so that you can monitor the installation and check for any errors.

-   Installs  the packages in your home directory. They will be available f
    or you to use across Quest nodes

-   Install Bioconductor packages with for eg 
    source("https://bioconductor.org/biocLite.R")
    biocLite("curatedBladderData")











