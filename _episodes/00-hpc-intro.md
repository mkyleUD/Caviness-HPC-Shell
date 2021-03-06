---
title: "What is the Caviness Cluster and Why Should You Use it?"
teaching: 25
exercises: 5
questions:
- "What is the Caviness Cluster and who can use it?"
- "What can I expect to learn from this course?"
objectives:
- "Understand the basics about the Caviness Cluster, who are its owners and who can use it."
- "Identify how the Caviness Cluster could benefit your research."
- "Know how Caviness may differ from other High Performance Computing (HPC) Systems but also 
other clusters here at the University of Delaware"
keypoints:
- "Caviness is like other HPC systems but does use a custom program (VALET) for setting up the 
   computing environment."
- "Caviness and HPC systems can be used to do work that would either be impossible or much slower on
  a local desktop or lab computer."
- "The standard method of interacting with most HPC systems is via a command line interface such as
  Bash."
---

## What is the Caviness Cluster?
The Caviness cluster is named in honor of Jane Caviness, the former director of Academic Computing
Services at the University of Delaware. In the 1980's, Jane Caviness led a groundbreaking expansion
of UD's computing resources and network infrastructure that laid the foundation for UD's current
research computing capabilities. 

Caviness is University of Delaware's (UD) third community cluster. It was deployed in July 2018 and 
is a distributed-memory Linux cluster. It is based on a rolling-upgradeable model for expansion and 
replacement of hardware over time. For more information on the specifics of Caviness hardware please
vist the [Caviness](https://docs.hpc.udel.edu/abstract/caviness/caviness) page.  The cluster was 
purchased with a proposed 5 year life for the first generation hardware, putting its refresh in the 
April 2023 to June 2023 time period. 

Caviness is a technical and financial partnership between UD's Information Technologies and UD's 
faculty and researchers who require high-performance computing resources. Faculty and researchers
become financial stakeholders by purchasing HPC resources (based on the cost of one or more compute
nodes) in the cluster. Only stakeholders and the researchers sponsored by a stakeholder may use the
cluster. It is located at UD's Computing Center.



## Why Use The Caviness Cluster
> ## What do you need?
>
> Talk to your neighbor about your research. How does computing help you do your research? How 
>could more computing help you do more or better research?
{: .challenge}

Frequently, research problems that use computing can outgrow the desktop or laptop computer where
they started:

* A statistics student wants to do cross-validate their model. This involves running the model 1000
  times -- but each run takes an hour. Running on their laptop will take over a month!
* A genomics researcher has been using small datasets of sequence data, but soon will be receiving 
  a new type of sequencing data that is 10 times as large. It's already challenging to open the
  datasets on their computer -- analyzing these larger datasets will probably crash it.
* An engineer is using a fluid dynamics package that has an option to run in parallel. So far, they
  haven't used this option on their desktop, but in going from 2D to 3D simulations, simulation 
  time has more than tripled and it might be useful to take advantage of that feature.

In all these cases, what is needed is access to more computers that can be used at the same time.
Luckily, large scale computing systems -- shared computing resources with lots of computers -- like
Caviness can be use to help with these problems. HPC systems similar to Caviness can be found at 
many other universities, labs, or through national networks. These resources usually have more 
central processing units(CPUs), CPUs that operate at higher speeds, more memory, more storage, and 
faster connections with other computer systems. They are frequently called "clusters", 
"supercomputers" or resources for "high performance computing" or HPC. In this lesson, we will 
usually use the terminology of HPC and HPC cluster.

Using a cluster often has the following advantages for researchers:

* **Speed.** With many more CPU cores, often with higher performance specs, than a typical laptop 
  or desktop, HPC systems can offer significant speed up.
* **Volume.** Many HPC systems have both the processing memory (RAM) and disk storage to handle 
  very large amounts of data. Terabytes of RAM and petabytes of storage are available for research
  projects.
* **Efficiency.** Many HPC systems operate a pool of resources that are drawn on by a many users. 
  In most cases when the pool is large and diverse enough the resources on the system are used 
  almost constantly.
* **Cost.** Bulk purchasing and government funding means that the cost to the research community for
  using these systems is significantly less than it would be otherwise.
* **Convenience.** Maybe your calculations just take a long time to run or are otherwise
  inconvenient to run on your personal computer. There's no need to tie up your own computer for
  hours when you can use someone else's instead.

This is how a large-scale compute system like a cluster can help solve problems like those listed 
at the start of the lesson.

> ## Thinking ahead
>
> How do you think using a large-scale computing system will be different from using your laptop?
> Talk to your neighbor about some differences you may already know about, and some
> differences/difficulties you imagine you may run into.
{: .challenge}

## Caviness Cluster compared to the other clusters at UD and other HPC systems.

The workload management software on Caviness is Slurm. It is commonly used for HPC systems 
but it is new to UD. The prior two community clusters used Grid 
Engine for their workload manager. For setting up your computing environment Caviness will 
continue to use VALET, just as Mills and Farber have used. VALET is a recursive acronym for VALET
Automates Linux Environment Tasks – is an alternative that strives to be as simple as possible to
configure your environment to use software installed on the cluster. VALET is unique to UD, 
if you have used another HPC system you might be 
familiar with the Environment Modules Package, more commonly known as modules. VALET and modules 
essentially perform the same services, but each have a different syntax in doing so. More details on VALET 
will be coming later on in the course.

## On Command Line

Using Caviness like most HPC systems involves the use of a shell through a command line interface 
(CLI) and either specialized software or programming techniques. The shell is a program with the 
special role of having the job of running other programs rather than doing calculations or similar
tasks itself. Whatever the user types, is passed to the shell, which then figures out what commands
to run and orders the computer to execute them. (Note that the shell is called "the shell" because it 
encloses the operating system in order to hide some of its complexity and make it simpler to 
interact with.) The most popular Unix shell is Bash, the Bourne Again SHell (so-called because it's
derived from a shell written by Stephen Bourne). Bash is the default shell on most modern 
implementations of Unix and in most packages that provide Unix-like tools for Windows.

Interacting with the shell is done via a command line interface (CLI) on most HPC systems. In the
earliest days of computers, the only way to interact with early computers was to rewire them. From
the 1950s to the 1980s most people used line printers. These devices only allowed input and output
of the letters, numbers, and punctuation found on a standard keyboard, so programming languages and
software interfaces had to be designed around that constraint and text-based interfaces were the 
way to do this. Typing-based interfaces are often called a **command-line interface**, or CLI, to
distinguish it from a **graphical user interface**, or GUI, which most people now use. The heart of
a CLI is a **read-evaluate-print loop**, or REPL: when the user types a command and then presses 
the Enter (or Return) key, the computer reads it, executes it, and prints its output. The user then
types another command, and so on until the user logs off.

Learning to use Bash or any other shell sometimes feels more like programming than like using a
mouse. Commands are terse (often only a couple of characters long), their names are frequently
cryptic, and their output is lines of text rather than something visual like a graph. However, 
using a command line interface can be extremely powerful, and learning how to use one will allow 
you to reap the benefits described above.

## The rest of this lesson

The only way to use these types of resources is by learning to use the command line. This
introduction to Caviness has two parts:

* We will learn to use the UNIX command line (also known as Bash).
* We will use our new Bash skills to connect to and operate a high-performance computing
  supercomputer.

The skills we learn here have other uses beyond Caviness or other HPC: Bash and UNIX skills are 
used everywhere, be it for web development, running software, or operating servers. It's become so
essential that Microsoft now
[ships it as part of Windows](https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6)!
Knowing how to use Bash and HPC systems will allow you to operate virtually any modern device. 
With all of this in mind, let's connect to a cluster and get started!


{% include links.md %}
