


# Interactive Session

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_275.png" alt="We are on the seventh and final step of the pathway." width="80%" style="display: block; margin: auto;" />

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

The CPU, or Central Processing Unit, is the brain of the computer that performs and orchestrates computational tasks. Modern computers often perform multiple tasks at once, ranging from 4 tasks on a typical laptop to 48 tasks or more on higher end servers. 

RAM, or Random Access Memory, is often simply referred to as memory. This short term memory holds the information that the CPU needs to perform calculations. One distinctive feature of memory is that it is short term. In other words, when the electricity is shut off, the data stored in memory disappears. To save the CPU's work, you usually save files to your computer. Running highly complicated analyses or algorithms can often require additional memory resources.

The [GPU](https://www.intel.com/content/www/us/en/products/docs/processors/what-is-a-gpu.html){target="_blank"}, or Graphics Processing Unit, is similar to the CPU. The GPU was originally designed to quickly render graphics (such as for video games), but today can be used to run complex artificial intelligence applications or computationally intensive jobs.

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_26.png" alt="CPU is the brain of the computer, whereas memory stores information in the short term." width="80%" style="display: block; margin: auto;" />

You will see that you are now logged on to "gizmo" instead of "rhino". Remember that the part of the cluster where you log in is called `rhino`. The part of the cluster where jobs are run is called `gizmo`. 

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_50.png" alt="Configuration prompts for interactive node log the user in to gizmo." width="100%" />

## Running Interactive Commands

You can start working on the node by running a similar command as we used in the job we submitted via script. Echo a message by running:

```
echo "Hello, again!"
```

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_58.png" alt="An echo message is printed on an interactive node." width="100%" />


## Using Pre-installed Software Modules

Let's get a bit more advanced. We can load a preconfigured software bundle called a module. This is very convenient because it means we don't need to install anything manually! In this example, we will load a module containing [R](https://www.r-project.org/){target="_blank"} version 4.2.0. You can learn more about what modules are available and how to request new ones for the Fred Hutch cluster [here](https://sciwiki.fredhutch.org/scicomputing/compute_scientificSoftware/){target="_blank"}.

```
ml fhR/4.2.0-foss-2021b
```

Next, launch R:

```
R
```

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_65.png" alt="The R module and R session have been launched on the interactive node." width="100%" />

You can play around with R here. For example, you might run:

```
head(mtcars)
```

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_72.png" alt="R commands on an interactive node." width="100%" />

Close the R session by typing:

```
q()
```

R will ask if you want to save your workspace. Type `n` for no and hit return.

Close the interactive node by typing:

```
exit
```

<img src="resources/images/07-interactive_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_82.png" alt="The R session and interactive node have been exited." width="100%" />

<div class = "dictionary">
`grabnode` 

This command starts an interactive session on the cluster.

**Node** 

One of the networked computers in the cluster. 

**CPU** 

A computer component that performs and orchestrates computational tasks.

**Memory** 

A computer component that stores calculations and information in the short term.
</div>
