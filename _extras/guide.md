---
layout: page
title: "Instructor Notes"
permalink: /guide/
---
*   Why do we learn to use the shell?
    *   It's important for working on remote machines, and allows researchers to access powerful machines.
    *   Allows users to automate repetitive tasks
*   The Problem
    *   Running the same workflow on several samples can be unnecessarily labor intensive
    *   Manual manipulation of data files:
        *   is often not captured in documentation
        *   is hard to reproduce
        *   is hard to troubleshoot, review, or improve
*   The Shell
    *   Workflows can be automated using shell scripts
    *   Built-in commands allow for easy data manipulation (e.g. sort, grep, etc.)
    *   Every step can be captured in the shell script and allow reproducibility and easy troubleshooting

## Preparing to Teach ##
The carpentry curriculum is design to be taught primarily for in person learning. However, efforts
have been made to make these lessons more friendly for the online environment. With that in mind 
there is flexibility to hold the lesson in-person, online, or in a hybrid style. The below 
information will help instructors design the lessons, and exercises for any style the lesson 
is being held in.

For all instructing styles it is important that the instructor goes through the lessons themselves to
familiarize themselves to any changes or updates that may have been added. Instructors should also 
remove and download a fresh copy of the [bash-lesson.tar.gz]({{ page.root }}{% link files/bash-lesson.tar.gz %})
. This will ensure that everyone in the lesson has all the same files and that all changes made during
prior lessons are eliminated.

## Overview

Many people have questioned whether we should still teach the shell.
After all,
anyone who wants to rename several thousand data files
can easily do so interactively in the Python interpreter,
and anyone who's doing serious data analysis
is probably going to do most of their work inside the IPython Notebook or R Studio.
So why teach the shell?

The first answer is,
"Because it enables use of many compute resources researchers cannot access otherwise."
Familiarity with the shell is very useful for remotely accessing machines,
using high-performance computing (HPC) infrastructure,
and running specialized tools for many disciplines.
While details on HPC are not fully covered in this lesson the groundwork for further development of these skills
will be covered.

In particular,
understanding the syntax of commands, flags, help systems, and
file system structure (and how to navigate it) are useful for remote access.

The second answer is,
"Because so much else depends on it."
Installing software,
configuring your default editor,
writing of scripts, and
many tools often use its terminology
(for example, the `%ls` and `%cd` magic commands in IPython).



Finally,
and perhaps most importantly,
teaching people the shell lets us teach them 
to think about programming in terms of function composition.
In the case of the shell,
this takes the form of pipelines rather than nested function calls,
but the core idea of "small pieces, loosely joined" is the same.

## Teaching in Person Lessons Notes 
For in person lessons  each learner needs their own computer with a connection to the internet. 
Before the lesson begins each learner should make sure they can access a terminal. Directions
on how to access or install terminal applications can be found in the 
lessons [setup page]({{site.url}}{{site.baseurl}}/setup). Learners may also want to bring something
to write with and on. 

## Teaching Online Lessons Notes
For the online format interactions and sharing of information can have its challenges. Online formats 
benefit from having two or more instructors. One who is the presenter, and the other(s) are helpers.
The use of software like `Zoom` and `Google Docs` or other similar software, help to create a virtual
classroom environment. 

In the virtual classroom the instructors are broken into two rolls, a presenter, and helper(s). The
presenter leads the lesson. They walked through the episodes, while sharing their screens with the learners. 
The helper hosts the virtual classroom. They are in control of making sure learners are muted and unmuted
at appropriate times. Additionally, they monitor the chatroom and help coordinate responses to 
questions. This can be a lot for just one helper, so if possible, having two helpers can be beneficial.

While `Zoom` or a similar software creates the virtual classroom, `Google Docs` creates a virtual whiteboard.
Creating and sharing a `Google Doc` with the learners and the instructor is a great way to create notes and
track attendance for each lesson. Having this open to everyone, instructors and learners creates a great form 
for people to add notes, ask questions, and respond to exercises. This document can also be left online 
after the lesson has ended so learners can access and review information as needed.

## Online Teaching Resources 
### Video Chat
 *  Google Hangout
 *  Zoom
 

### Collaborating Text Resources
 *  Etherpad
 *  Google Docs

> ## Important Note
>
>  If the online lesson is going to be recorded make sure to check all rules and guidelines to ensure that 
>  there are no violations to privacy rules and regulations for the learners, and that everyone is aware 
>  that the session is, or could be recorded. 
>
{: .callout}


## Teaching Hybrid Online/In Person Lessons
More information still to come. 
