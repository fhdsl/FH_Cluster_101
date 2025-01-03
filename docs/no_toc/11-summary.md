


# Summary

Let's review the key information from the previous sections.

## Overview

A [computing cluster](#what-is-a-cluster) is a set of computers networked together to perform large tasks. We usually connect to the cluster using a command-line interface called a [Terminal](#terminal). The Terminal application varies based on your operating system. We connect to the cluster using a secure method called [SSH](#logging-in). Exact SSH commands vary depending on your operating system.

Before using the Fred Hutch cluster, it's a good idea to [contact the SciComp](#account-setup) team to ensure your account is set up correctly. You must be connected to the campus wifi network, plugged into a networked ethernet jack, or connected to the Fred Hutch VPN to connect to the Fred Hutch cluster.

Computer tasks are typically performed via job submission, where you tell the cluster what to do inside a script file. The Fred Hutch cluster uses [Slurm](#submit-your-first-job) to organize jobs submitted by different users. When building, testing, and debugging jobs, you might want to launch an [interactive session](#interactive-session) on the cluster. You will be asked several questions about resources before your session starts.

You can use the application [Cyberduck](#file-upload-and-download) to transfer smaller files between your local computer and the cluster via SFTP (SSH File Transfer Protocol). This course does not cover transferring sensitive data, which requires extra precautions.

Don't be afraid to ask for [help](#help)! Check out the SciWiki, join the Slack workspace, or contact the SciComp team if you get stuck.

## Glossary

- **computing cluster** - A set of computers networked together to perform large tasks.
- **CPU** - A computer component that performs and orchestrates computational tasks.
- **Cyberduck** - Third-party software which transfers files between your local machine and the cluster.
- **hostname** - The hostname is the name, or label, assigned to a computer in a network. We connect to hostname `rhino.fhcrc.org` or `rhino` for short.
- **memory** - A computer component that stores calculations and information in the short term.
- **node** - A part of the cluster; a computer in the network.
- **SSH** - A secure method for remotely connecting to another computer or network of computers; stands for “Secure SHell”.
- **terminal** - A command line interface; a software application that allows you to issue commands directly to a computer.

## Commands (command line interface)

| Command    | Description                                  | Usage                    |
|------------|----------------------------------------------|--------------------------|
| `cat`      | displays all contents of a file              | `cat [filename]`         |
| `exit`     | terminates an interactive session            | `exit`                   |
| `grabnode` | launches an interactive session              | `grabnode`               |
| `ls`       | lists files in the current folder            | `ls`                     |
| `sbatch`   | submits a script containing job instructions requesting custom cores | `sbatch -c [cores] [scriptname.sh]` |
| `squeue`   | lists job submission status for the current user    | `squeue --me`     |
| `scancel`  | cancel job submission by job ID              | `scancel [job ID]`       |
| `wget`     | downloads a file from the internet           | `wget [url]`             |
