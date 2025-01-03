


# Interactive Session


\begin{center}\includegraphics[width=0.8\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_275} \end{center}

While using the cluster, you might need to build and test scripts interactively before running them. Luckily, you can work directly on the cluster by creating an interactive session. When you launch an interactive session, the cluster assigns you a portion of the networked computers called a "node". This node (or part of one) is dedicated to you for a period of time rather than using the Slurm job submission system. 

Because an interactive session takes up resources directly on the cluster whether you're actively using it or not, it's best to use interactive sessions only when a task cannot be done by submitting a script.  

## Starting the session

When starting an interactive session, you're going to need to think about what you are testing and what resources you might need on the node you are requesting to use. You can always start an interactive session using the default values if you aren't sure what you need yet.  

Start an interactive session on a node by running the command:

```
grabnode
```

You will be prompted with several questions about the type of resources on the node you want. We don't need anything fancy, so we will set up the session to use minimal resources. You can enter the following:

- _How many CPUs/cores would you like to grab on the node?_ **1**
- _How much memory (GB) would you like to grab?_ **20**
- _Please enter the max number of days you would like to grab this node:_ **1**
- _Do you need a GPU?_ **N**
- When prompted, enter your password

You requested 1 CPU, 20GB of RAM, and don't need a GPU. The [GPU](https://www.intel.com/content/www/us/en/products/docs/processors/what-is-a-gpu.html){target="_blank"}, or Graphics Processing Unit, is similar to the CPU. The GPU was originally designed to quickly render graphics (such as for video games), but today can be used to run complex artificial intelligence applications or computationally intensive jobs.


\begin{center}\includegraphics[width=0.8\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_26} \end{center}

You will see that you are now logged on to the compute node "gizmo" instead of the login node "rhino". Remember that the part of the cluster where you log in is called `rhino`. The part of the cluster where jobs are run is called `gizmo`. 


\includegraphics[width=1\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_50} 

## Running Interactive Commands

You can start working on the node by running a similar command as we used in the job we submitted via script. Echo a message by running:

```
echo "Hello, again!"
```


\includegraphics[width=1\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_58} 


## Using Pre-installed Software Modules

Let's get a bit more advanced. We can load a preconfigured software bundle called a module. This is very convenient because it means we don't need to install anything manually! In this example, we will load a module containing [R](https://www.r-project.org/){target="_blank"} version 4.2.0. You can learn more about what modules are available and how to request new ones for the Fred Hutch cluster [here](https://sciwiki.fredhutch.org/scicomputing/compute_scientificSoftware/){target="_blank"}.

```
ml fhR/4.2.0-foss-2021b
```

Next, launch R:

```
R
```


\includegraphics[width=1\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_65} 

You can play around with R here. For example, you might run:

```
head(mtcars)
```


\includegraphics[width=1\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_72} 

Close the R session by typing:

```
q()
```

R will ask if you want to save your workspace. Type `n` for no and hit return.

Close the interactive node by typing:

```
exit
```


\includegraphics[width=1\linewidth]{resources/images/09-interactive_files/figure-latex//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_82} 


### Loading Modules in non-interactive mode

You have just seen how to load in software modules in the interactive mode. When you launch a job via `sbatch` to start computing on the compute nodes, you may also need to load in software modules. You can add the `ml` command within your shell script, such as the following:

```
#!/bin/bash

ml fhR/4.2.0-foss-2021b
Rscript my_r_script.R
```


<div class = "dictionary">

`grabnode`

This command starts an interactive session on the cluster.

</div>

