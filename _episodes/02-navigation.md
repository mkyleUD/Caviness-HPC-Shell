---
title: "Navigating the Caviness File Structure"
teaching: 30 
exercises: 5
questions:
- "How do I navigate and start interacting with files and directories on Caviness?"
- "How do I track where I am at?"
objectives:
- Learn how to navigate around directories and look at their contents
- Explain the difference between a file and a directory.
- Translate an absolute path into a relative path and vice versa.
- Identify the actual command, flags, and filenames in a command-line call.
- Demonstrate the use of tab completion, and explain its advantages.
keypoints:
- "Your current directory is referred to as the working directory."
- "To change directories, use `cd`."
- "To view files, use `ls`."
- "You can view help for a command with `man command` or `command --help`."
- "Hit the <kbd>TAB</kbd> key to autocomplete whatever you're currently typing."
---

At this point in the lesson, we've just logged into the system. Nothing has happened yet, and we're
not going to be able to do anything until we learn a few basic commands. In this lesson we will talk
about `ls`, `cd`, and a few other commands. These commands will help you navigate around not only the
 {{ site.workshop_host }} File structure but nearly any Linux/Unix File system using the CLI. 
~~~
for thing in collection:
    do_something
~~~
{: .source}


Right now, all we see is something that looks like this:

~~~
{{ site.workshop_host_prompt }}
~~~
{: .language-bash}

The dollar sign is a **prompt**, which shows us that the shell is waiting for input. If you do not 
see the dollar sign, then the system is not ready for your next input. This applies for the duration
of your session. Later, we will talk about what happens if a command is entered and a `$` prompt does
not return to your screen. When typing commands, either from these lessons or from other sources,
**do not type** the prompt `$`, only the commands that follow it.

Type the command `whoami`, then press the <kbd>enter</kbd> key (sometimes marked Return) to send the
command to the shell. The command's output is the ID of the current user, i.e., it shows us who the 
shell
thinks we are:

~~~
$ whoami
~~~
{: .language-bash}
~~~
{{ site.workshop_host_id}}
~~~
{: .output}

More specifically, when we type `whoami` the shell:

1.  finds a program called `whoami`,
2.  runs that program,
3.  displays that program's output, then
4.  displays a new prompt to tell us that it's ready for more commands.

Next, let's find out where we are by running a command called `pwd` (which stands for "print working
directory"). At any moment, our **current working directory** (where we are) is the directory that
the computer assumes we want to run commands in unless we explicitly specify something else. Here,
the computer's response is `{{ site.workshop_host_homedir }}`, which is user
`{{ site.workshop_host_id}}`'s  **home directory**.

**Note** that the location of your home directory may differ from system to system.

~~~
$ pwd
~~~
{: .language-bash}
~~~
{{ site.workshop_host_homedir }}
~~~
{: .output}

So, we know where we are. How do we look and see what's in our current directory?
~~~
$ ls
~~~
{: .language-bash}

`ls` prints the names of the files and directories in the current directory in alphabetical order,
arranged neatly into columns.

> ## Differences between remote and local system
> 
> Open a second terminal window on your local computer and run the `ls` command without logging in
> remotely. What differences do you see?
> **Note:** Window users will not be able to do this with PuTTY, Since PuTTY only opens remote
> conncetions. 
>
> > ## Solution
> > You would likely see something more like this:
> > ~~~
> > Applications Documents    Library      Music        Public
> > Desktop      Downloads    Movies       Pictures
> > ~~~
> > In addition, you should also note that the text before the prompt (`$`) is different. This is
> > very important for making sure you know what system you are issuing commands on when in the shell.
> {: .solution}
{: .challenge}

If nothing shows up when you run `ls`, it means that nothing's there. Let's make a directory for us
to play with.

`mkdir <new directory name>` makes a new directory with that name in your current location. Notice
that this command required two pieces of input: the actual name of the command (`mkdir`) and an
argument that specifies the name of the directory you wish to create.

~~~
$ mkdir training
~~~
{: .language-bash}

Let's us `ls` again. What do we see?
~~~
training
~~~
{: .output}

Our folder is there, awesome. What if we wanted to go inside it and do stuff there? We will use the
`cd` (change directory) command to move around. Let's `cd` into our new training folder.

~~~
$ cd training
$ pwd
~~~
{: .language-bash}
~~~
{{ site.workshop_host_homedir }}/training
~~~
{: .output}

Now that we know how to use `cd`, we can go anywhere. That's a lot of responsibility. What happens
if we get "lost" and want to get back to where we started?

To go back to your home directory, the following two commands will work:

~~~
$ cd {{ site.workshop_host_homedir }}
$ cd ~
~~~
{: .language-bash}

What is the `~` character? When using the shell, `~` is a shortcut that represents
`{{ site.workshop_host_homedir }}`.

A quick note on the structure of a UNIX (Linux/Mac/Android/Solaris/etc) filesystem. Directories and
absolute paths (i.e. exact position in the system) are always prefixed with a `/`. `/` is the "root"
or base directory.

Let's go there now, look around, and then return to our home directory.

~~~
$ cd /
$ ls
~~~
{: .language-bash}
~~~
bin   dev  home  lib64   media  opt   root  sbin  sys  ttt  var
boot  etc  lib   lustre  mnt    proc  run   srv   tmp  usr  work
~~~
{: .output}

The "home" directory is the one where we generally want to keep all of our files. Other folders on a
UNIX OS contain system files, and get modified and changed as you install new software or upgrade
your OS.
> ## Returning to your home directory
>
> From the root directory please provide three different ways of getting back to your home 
>directory.
>
> > ## Solution
> > 
> > 1. `cd` - Shortcut
> > 
> > 2. `cd ~` - Shorthand
> > 
> > 3. `cd {{ site.workshop_host_homedir }}` - This is the absolute path
> {: .solution}
{: .challenge}


> ## Using HPC filesystems
> On HPC systems, you have a number of places where you can store your files. These differ in both
> the amount of space allocated and whether they are backed up or not.
> Caviness has three different area where you can store files. Each of the different area serve 
> different purposes. They also have different amounts of storage and are backed up differently as 
> well.
>
> File storage locations:
>
> * **Home Directory Storage** -  Each user has 20 GB of disk storage reserved for personal use on 
>   the home file system. Users' home directories are in /home (e.g., /home/1201), and the directory
>   name is put in the environment variable `$HOME` at login. The permanent file system is configured 
>   to allow nearly instantaneous, consistent snapshots. The snapshot contains the original version 
>   of the file system, and the live filesystem contains any changes made since the snapshot was 
>   taken. In addition, all your files are regularly replicated at UD's off-campus disaster recovery 
>   site. You can use read-only snapshots to revert a previous version, or request to have your files
>   restored from the disaster recovery site.
>
>   You can check to see the size and usage of your home directory with the command 
>   ~~~
>   df -h $HOME
>   ~~~
> * **Work Group Storage** -  Each research group has at least 1000 GB of shared group (workgroup) 
>   storage in the `/work` directoryidentified by the `«investing_entity»` (e.g., `/work/it_css`) and is
>   referred to as your workgroup directory. This is used for input files, supporting data files, 
>   work files, and output files, source code and executables that need to be shared with your 
>   research group. Just as your home directory, read-only snapshots of workgroup's files are made 
>   several times for the passed week. In addition, the filesystem is replicated on UD's off-campus 
>   disaster recovery site. Snapshots are user-accessible, and older files may be retrieved by special 
>   request.
>
>   You can check the size and usage of your workgroup directory by using the workgroup command to 
>   spawn a new workgroup shell, which sets the environment variable `$WORKDIR` 
>   ~~~
>   df -h $WORKDIR
>   ~~~
>
> *High-performance filesystem:*   
> * **Lustre Storage** - User storage is available on a high-performance Lustre-based filesystem 
>   having 210 TB of usable space. This is used for temporary input files, supporting data files, 
>   work files, and output files associated with computational tasks ran on the cluster. The 
>   filesystem  is accessible to all of the processor cores via Omni-path Infiniband. 
>
>   The Lustre filesystem is not backed up nor are there snapshots to recover deleted files. However,
>   it is a robust RAID-6 system. Thus, the filesystem can survive a concurrent disk failure of two
>   independent hard drives and still rebuild its contents automatically. 
>   
>   All users have access the public scratch directory (`/lustre/scratch`). 
>
>
>   *A full system inhibits use for everyone potentially preventing jobs from running. Therefore IT staff may run cleanup procedures as needed to purge aged files or directories in 
>   Lustre if old files are degrading system performance.* 
{: .callout}

There are several other useful shortcuts you should be aware of.

- `.` represents your current directory
- `..` represents the "parent" directory of your current location
- While typing nearly *anything*, you can have bash try to autocomplete what you are typing by
  pressing the `tab` key.

Let's try these out now:

~~~
$ cd ./training
$ pwd
$ cd ..
$ pwd
~~~
{: .language-bash}

~~~
{{ site.workshop_host_homedir }}/training
{{ site.workshop_host_homedir }}
~~~
{: .output}

Many commands also have multiple behaviours that you can invoke with command line 'flags.' What is a
flag? It's generally just your command followed by a `-` or `--` and the name of the flag.
You follow the flag(s) with any additional arguments you
might need.

We're going to demonstrate a couple of these "flags" using `ls`.

Show hidden files with `-a`. Hidden files are files that begin with `.`, these files will not appear
otherwise, but that doesn't mean they aren't there! "Hidden" files are not hidden for security
purposes, they are usually just config files and other tempfiles that the user doesn't necessarily
need to see all the time.

~~~
$ ls -a
~~~
{: .language-bash}

~~~
.  ..  .bash_history .bash_logout  .bash_profile  .bashrc .bash_udit  training  .ssh  

~~~
{: .output}

Notice how both `.` and `..` are visible as hidden files. 

To show files, their size in bytes, date last modified, permissions, and other 
things with `-l`.

~~~
$ ls -l
~~~
{: .language-bash}
~~~
drwxr-xr-x  2 traine everyone     2 Jul 13 15:48 training

~~~
{: .output}

This is a lot of information to take in at once, but we will explain this later! `ls -l` is
*extremely* useful, and tells you almost everything you need to know about your files without
actually looking at them.

We can also use multiple flags at the same time!

~~~
$ ls -l -a
~~~
{: .language-bash}

~~~
{{ site.workshop_host_prompt }} ls -la
total 36
drwx--x--x 17 traine everyone    29 Jul 21 14:22 .
drwxr-xr-x 79 root  root         0 Jul 21 14:23 ..
-rw-------  1 traine it_css   20442 Jul 21 15:24 .bash_history
-rw-r--r--  1 traine everyone    17 Jul 25  2018 .bash_logout
-rw-r--r--  1 traine everyone   200 Jul 25  2018 .bash_profile
-rw-r--r--  1 traine everyone   384 Mar 19 15:21 .bashrc
-rw-r--r--  1 traine everyone  1154 Mar 24 10:16 .bash_udit
drwxr-xr-x  2 traine everyone     2 Jul 13 15:48 training
drwx------  2 traine everyone      6 Mar 18  2020 .ssh
-rw-------  1 traine everyone   1007 Oct 15 11:29 .Xauthority
~~~
{: .output}

Flags generally precede any arguments passed to a UNIX command. `ls` actually takes an extra
argument that specifies a directory to look into. When you use flags and arguments together, they
syntax (how it's supposed to be typed) generally looks something like this:

~~~
$ command <flags/options> <arguments>
~~~
{: .language-bash}

So using `ls -l -a` on a different directory than the one we're in would look something like:
####inputs
~~~
$ ls -l -a ~/training
~~~
{: .language-bash}
####outputs
~~~
drwxr-sr-x 2 yourUsername tc001 4096 Nov 28 09:58 .
drwx--S--- 5 yourUsername tc001 4096 Nov 28 09:58 ..
~~~
{: .output}

Another useful flag is the `-F` flag. The `-F` appends indicators to entries which helps you 
identify files verus directories.
~~~
ls -F -la
~~~
{: .language-bash}
~~~
drwx--x--x 17 traine everyone    29 Jul 21 14:22 ./
drwxr-xr-x 79 root  root         0 Jul 21 14:23 ../
-rw-------  1 traine it_css   20442 Jul 21 15:24 .bash_history
-rw-r--r--  1 traine everyone    17 Jul 25  2018 .bash_logout
-rw-r--r--  1 traine everyone   200 Jul 25  2018 .bash_profile
-rw-r--r--  1 traine everyone   384 Mar 19 15:21 .bashrc
-rw-r--r--  1 traine everyone  1154 Mar 24 10:16 .bash_udit
drwxr-xr-x  2 traine everyone     2 Jul 13 15:48 training/
drwx------  2 traine everyone      6 Mar 18  2020 .ssh/
-rw-------  1 traine everyone   1007 Oct 15 11:29 .Xauthority
~~~
{: .output}
As you can see in the above output rows that end with a `/` are directories. The rows that don't 
end with a `/` are files.

## Where to go for help?

How did I know about the `-l` and `-a` options? Is there a manual we can look at for help when we
need help? There is a very helpful manual for most UNIX commands: `man` (if you've ever heard of a
"man page" for something, this is what it is).

~~~
$ man ls
~~~
{: .language-bash}

~~~
LS(1)                                                   User Commands                                                  LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about the FILEs (the current directory by default).  Sort entries alphabetically if none of -cftu‐
       vSUX nor --sort is specified.

       Mandatory arguments to long options are mandatory for short options too.
Manual page ls(1) line 1 (press h for help or q to quit)
~~~
{: .output}

To navigate through the `man` pages, you may use the up and down arrow keys to move line-by-line, or
try the spacebar and "b" keys to skip up and down by full page. Quit the `man` pages by typing "q".

Alternatively, most commands you run will have a `--help` option that displays addition information
For instance, with `ls`:

~~~
$ ls --help
~~~
{: .language-bash}

~~~
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
      --author               with -l, print the author of each file
  -b, --escape               print C-style escapes for nongraphic characters
      --block-size=SIZE      scale sizes by SIZE before printing them; e.g.,
                               '--block-size=M' prints sizes in units of
                               1,048,576 bytes; see SIZE format below
  -B, --ignore-backups       do not list implied entries ending with ~

# further output omitted for clarity
~~~
{: .output}

> ## Unsupported command-line options
> If you try to use an option that is not supported, `ls` and other programs will print an error
> message similar to this:
>
> ~~~
> {{ site.workshop_host_prompt }}$ ls -j
> ~~~
> {: .language-bash}
> 
> ~~~
> ls: invalid option -- 'j'
> Try 'ls --help' for more information.
> ~~~
> {: .error}
{: .callout}


> ## Looking at documentation
>
> Looking at the man page for `ls` or using `ls --help`, what does the `-h` (`--human-readable`)
> option do?
>
> > ## Solution
> >  `-h, --human-readable:  with -l, print sizes in human readable format (e.g., 1K 234M 2G)`
> {: .solution}
{: .challenge}

> ## Absolute vs Relative Paths
>
> Starting from `/Users/amanda/data/`, which of the following commands could Amanda use to navigate
> to her home directory, which is `/Users/amanda`?
>
> 1. `cd .`
> 2. `cd /`
> 3. `cd /home/amanda`
> 4. `cd ../..`
> 5. `cd ~`
> 6. `cd home`
> 7. `cd ~/data/..`
> 8. `cd`
> 9. `cd ..`
>
> > ## Solution
> > 1. No: `.` stands for the current directory.
> > 2. No: `/` stands for the root directory.
> > 3. No: Amanda's home directory is `/Users/amanda`.
> > 4. No: this goes up two levels, i.e. ends in `/Users`.
> > 5. Yes: `~` stands for the user's home directory, in this case `/Users/amanda`.
> > 6. No: this would navigate into a directory `home` in the current directory if it exists.
> > 7. Yes: unnecessarily complicated, but correct.
> > 8. Yes: shortcut to go back to the user's home directory.
> > 9. Yes: goes up one level.
> {: .solution}
{: .challenge}

> ## Relative Path Resolution
>
> Using the filesystem diagram below, if `pwd` displays `/home/1201/development`, what will `ls -F ../back_up`
> display?
>
> 1.  `../back_up: No such file or directory`
> 2.  `beta_v4/`
> 3.  `2019-10-28/ 2020-01-25/ 2020-07-05/`
> 4.  `beta_v5/ back_up/`
>
> ![File System for Challenge Questions](../fig/file_structure_1.png)
>
> > ## Solution
> > 1. No: there *is* a directory `back_up` in `/home/1201`.
> > 2. No: this is the content of `/home/1201/development/back_up`.
> > 3. Yes: this is the contents of `/home/1201/back_up`.
> > 4. No: this would be the contents of `/home/1201/development` or `./`.
> {: .solution}
{: .challenge}

> ## `ls` Reading Comprehension
>
> Assuming a directory structure as in the above Figure (File System for Challenge Questions), if
> `pwd` displays `/home/1201/development`, and `-r` tells `ls` to display things in reverse order, what
> command will display:
>
> ~~~
> beta_v5/ back_up/
> ~~~
> {: .output}
>
> 1.  `ls pwd`
> 2.  `ls -r -F`
> 3.  `ls -r -F /home/1201/development`
> 4.  Either #2 or #3 above, but not #1.
>
> > ## Solution
> >  1. No: `pwd` is not the name of a directory.
> >  2. Yes: `ls` without directory argument lists files and directories
> >     in the current directory.
> >  3. Yes: uses the absolute path explicitly.
> >  4. Correct: see explanations above.
> {: .solution}
{: .challenge}

> ## Exploring More `ls` Arguments
>
> What does the command `ls` do when used with the `-l` and `-h` arguments?
>
> Some of its output is about properties that we do not cover in this lesson (such as file
> permissions and ownership), but the rest should be useful nevertheless.
>
> > ## Solution
> > The `-l` arguments makes `ls` use a **l**ong listing format, showing not only the file/directory
> > names but also additional information such as the file size and the time of its last
> > modification. The `-h` argument makes the file size "**h**uman readable", i.e. display something
> > like `5.3K` instead of `5369`.
> {: .solution}
{: .challenge}

> ## Listing Recursively and By Time
>
> The command `ls -R` lists the contents of directories recursively, i.e., lists their
> sub-directories, sub-sub-directories, and so on in alphabetical order at each level. The command
> `ls -t` lists things by time of last change, with most recently changed files or directories
> first. In what order does `ls -R -t` display things? Hint: `ls -l` uses a long listing format to
> view timestamps.
>
> > ## Solution
> >
> > The directories are listed alphabetical at each level, the files/directories in each directory
> > are sorted by time of last change.
> {: .solution}
{: .challenge}
{% include links.md %}
