


# (PART\*) Introduction {-}

# What is a Cluster {#what-is-a-cluster}

<img src="resources/images/01-cluster_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_gff2211b72f_1_114.png" alt="We are on the first step of the pathway." width="80%" style="display: block; margin: auto;" />

A computing cluster is a set of many computers networked together. Because there are many computers working together, the network is able to handle computationally expensive tasks, like genome assemblies or advanced algorithms. Imagine you're building a house. It would take a long time by yourself! It's much better to have many builders working together.

Now that we have a team of workers, the next challenge is task management. A home construction team will need a manager to help delegate tasks. Similarly, the computing cluster uses management software to prioritize tasks, delegate workers (resources), and check on progress. The Fred Hutch cluster uses a common management and scheduling tool called [Slurm](https://slurm.schedmd.com/overview.html){target="_blank"}.

<img src="resources/images/01-cluster_files/figure-html//1BQxrVYdKZTbpCaF-i_q9w7s9x034lEXpQZDU-Sl09cs_g149d37dd4a1_0_18.png" alt="Your computer has 1 node, 8 CPUs, and 8 gigabytes of memory. The Hutch cluster has nearly 600 nodes, 4000 CPUs, and 40 terabytes of memory." width="80%" style="display: block; margin: auto;" />

How is the cluster different from a laptop or desktop? First, on your laptop you most likely interact with it using an operating system like Windows or MacOS. The Fred Hutch cluster uses a Linux operating system. Second, because many people use the cluster for many tasks, there isn't a central screen and keyboard. You access the cluster remotely from your computer! We will talk more about how to connect to the cluster in a [following chapter](#terminal).

<div class = "dictionary">
**Computing cluster**  
  
A set of computers networked together to perform large tasks.
</div>
