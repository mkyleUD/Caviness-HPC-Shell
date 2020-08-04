---
layout: reference
permalink: /reference/
---

## Summary of Basic Commands

| Action              | Files | Folders      |
|---------------------|-------|--------------|
| Inspect             | ls    | ls           |
| View all content    | cat   | ls           |
| View limited content| less  |              |
| Navigate to         |       | cd           |
| Move                | mv    | mv           |
| Copy                | cp    | cp -r        |
| Create              | touch |              |
| Edit or Create      | nano  | mkdir        |
| Delete (PERMANENTLY)| rm    | rmdir, rm -r |

## Filesystem hierarchy

The following is a generic overview of a standard Unix filesystem and does
not reflect {{ site.workshop_host }}'s actual filesystem.
The exact hierarchy depends on the platform,
so you may not see exactly the same files/directories on your computer:

![Linux filesystem hierarchy](../fig/standard-filesystem-hierarchy.svg)

## Glossary

{:auto_ids}
absolute path
:   A [path](#path) that refers to a particular location in a file system.
    Absolute paths are usually written with respect to the file system's
    [root directory](#root-directory),
    and begin with either "/" (on Unix) or "\\" (on Microsoft Windows).
    See also: [relative path](#relative-path).

argument
:   A value given to a function or program when it runs.
    The term is often used interchangeably (and inconsistently) with [parameter](#parameter).

command shell
:   See [shell](#shell)

command-line interface
:   A user interface based on typing commands,
    usually at a [REPL](#read-evaluate-print-loop).
    See also: [graphical user interface](#graphical-user-interface).

comment
:   A remark in a program that is intended to help human readers understand what is going on,
    but is ignored by the computer.
    Comments in Python, R, and the Unix shell start with a `#` character and run to the end of the line;
    comments in SQL start with `--`,
    and other languages have other conventions.


current working directory
:   The directory that [relative paths](#relative-path) are calculated from;
    equivalently,
    the place where files referenced by name only are searched for.
    Every [process](#process) has a current working directory.
    The current working directory is usually referred to using the shorthand notation `.` (pronounced "dot").

file system
:   A set of files, directories, and I/O devices (such as keyboards and screens).
    A file system may be spread across many physical devices,
    or many file systems may be stored on a single physical device;
    the [operating system](#operating-system) manages access.

filename extension
:   The portion of a file's name that comes after the final "." character.
    By convention this identifies the file's type:
    `.txt` means "text file", `.png` means "Portable Network Graphics file",
    and so on. These conventions are not enforced by most operating systems:
    it is perfectly possible (but confusing!) to name an MP3 sound file `homepage.html`.
    Since many applications use filename extensions to identify the [MIME type](#mime-type) of the file,
    misnaming files may cause those applications to fail.

filter
:   A program that transforms a stream of data.
    Many Unix command-line tools are written as filters:
    they read data from [standard input](#standard-input),
    process it, and write the result to [standard output](#standard-output).

flag
:   A terse way to specify an option or setting to a command-line program.
    By convention Unix applications use a dash followed by a single letter,
    such as `-v`, or two dashes followed by a word, such as `--verbose`,
    while DOS applications use a slash, such as `/V`.
    Depending on the application, a flag may be followed by a single argument, as in `-o /tmp/output.txt`.

for loop
:   A loop that is executed once for each value in some kind of set, list, or range.
    See also: [while loop](#while-loop).

FTP
:
   A protocol or utility which is used to transfer over a network connection. For security, user SFTP.

graphical user interface
:   A user interface based on selecting items and actions from a graphical display,
    usually controlled by using a mouse.
    See also: [command-line interface](#command-line-interface).

home directory
:   The default directory associated with an account on a computer system.
    By convention, all of a user's files are stored in or below her home directory.

High-Performance Computing (HPC)
:
    High Performance Computing is the term often used for large-scale computers and the simulations and
    models which run on them. 

Linux
:
    Linux is an operating system, similar to UNIX, which is becoming quite popular for supercomputers due
    to abundant support, user familiarity, and comparable performance with optimized UNIX systems. 
    Kraken, for example, runs on a modified version of Linux.

loop
:   A set of instructions to be executed multiple times. Consists of a [loop body](#loop-body) and (usually) a
    condition for exiting the loop. See also [for loop](#for-loop) and [while loop](#while-loop).

loop body
:   The set of statements or commands that are repeated inside a [for loop](#for-loop)
    or [while loop](#while-loop).

MIME type
:   MIME (Multi-Purpose Internet Mail Extensions) types describe different file types for exchange on the Internet,
    for example images, audio, and documents.

node
:
    In traditional computing, a node is an object on a network. For example, on a home network, your 
    computer, router, and printer might all be nodes. Supercomputers like Kraken are essentially networks,
    with nodes that communicate with each other to solve a larger problem than any singular computer could
    in a reasonable amount of time. Kraken contains several types of nodes; compute nodes are the work-horses
    of the system, and are much like a stripped-down computer. An I/O node is the interface between the compute
    nodes and other computers, that is, it deals with input and output for the system.

operating system
:   Software that manages interactions between users, hardware, and software [processes](#process). Common
    examples are Linux, macOS, and Windows.

orthogonal
:   To have meanings or behaviors that are independent of each other.
    If a set of concepts or tools are orthogonal,
    they can be combined in any way.

parameter
:   A variable named in a function's declaration that is used to hold a value passed into the call.
    The term is often used interchangeably (and inconsistently) with [argument](#argument).

parent directory
:   The directory that "contains" the one in question.
    Every directory in a file system except the [root directory](#root-directory) has a parent.
    A directory's parent is usually referred to using the shorthand notation `..` (pronounced "dot dot").

path
:   A description that specifies the location of a file or directory within a [file system](#file-system).
    See also: [absolute path](#absolute-path), [relative path](#relative-path).


pipe
:   A connection from the output of one program to the input of another.
    When two or more programs are connected in this way, they are called a "pipeline".

process
:   A running instance of a program, containing code, variable values,
    open files and network connections, and so on.
    Processes are the "actors" that the [operating system](#operating-system) manages;
    it typically runs each process for a few milliseconds at a time
    to give the impression that they are executing simultaneously.


prompt
:   A character or characters display by a [REPL](#read-evaluate-print-loop) to show that
    it is waiting for its next command.

quoting
:   (in the shell):
    Using quotation marks of various kinds to prevent the shell from interpreting special characters.
    For example, to pass the string `*.txt` to a program,
    it is usually necessary to write it as `'*.txt'` (with single quotes)
    so that the shell will not try to expand the `*` wildcard.

read-evaluate-print loop
:   (REPL): A [command-line interface](#command-line-interface) that reads a command from the user,
    executes it, prints the result, and waits for another command.

redirect
:   To send a command's output to a file rather than to the screen or another command,
    or equivalently to read a command's input from a file.

regular expression
:   A pattern that specifies a set of character strings.
    REs are most often used to find sequences of characters in strings.

relative path
:   A [path](#path) that specifies the location of a file or directory
    with respect to the [current working directory](#current-working-directory).
    Any path that does not begin with a separator character ("/" or "\\") is a relative path.
    See also: [absolute path](#absolute-path).

root directory
:   The top-most directory in a [file system](#file-system).
    Its name is "/" on Unix (including Linux and macOS) and "\\" on Microsoft Windows.

scratch space
:
    Supercomputers generally have what is called scratch space; disk space available for 
    temporary use. It is analogous to scratch paper. This may be thought of as a desk, 
    it is where papers are stored while they are waiting to be worked on or filed away.

shell
:   A [command-line interface](#cli) such as Bash (the Bourne-Again Shell)
    or the Microsoft Windows DOS shell
    that allows a user to interact with the [operating system](#operating-system).

shell script
:   A set of [shell](#shell) commands stored in a file for re-use.
    A shell script is a program executed by the shell;
    the name "script" is used for historical reasons.

SSH
:
    A protocol for securely connecting to a remote computer, or also a program which uses this 
    protocol. This connection is generally for a command line interface, but it is possible to 
    use GUI programs through SSH. For more information about how to use SSH, see Access. 

standard input
:   A process's default input stream.
    In interactive command-line applications,
    it is typically connected to the keyboard;
    in a [pipe](#pipe),
    it receives data from the [standard output](#standard-output) of the preceding process.


standard output
:   A process's default output stream.
    In interactive command-line applications,
    data sent to standard output is displayed on the screen;
    in a [pipe](#pipe),
    it is passed to the [standard input](#standard-input) of the next process.


sub-directory
:   A directory contained within another directory.

tab completion
:   A feature provided by many interactive systems in which
    pressing the Tab key triggers automatic completion of the current word or command.

UNIX
:
    UNIX is an operating system first developed in the 1970's. It has gone through a 
    number of incarnations, and still has many popular versions. UNIX has dominated 
    supercomputing for many years, however, the high performance computing community 
    has been increasingly turning to Linux for an operating system.

variable
:   A name in a program that is associated with a value or a collection of values.

while loop
:   A loop that keeps executing as long as some condition is true.
    See also: [for loop](#for-loop).

wildcard
:   A character used in pattern matching.
    In the Unix shell,
    the wildcard `*` matches zero or more characters,
    so that `*.txt` matches all files whose names end in `.txt`.

## External references

### Opening a terminal
* [Using the Terminal program on a Macintosh computer](https://services.udel.edu/TDClient/32/Portal/KB/ArticleDet?ID=477)
* [Using X-Windows (X11) and secure shell (SSH) to connect to a remote UNIX 
  server](https://services.udel.edu/TDClient/32/Portal/KB/ArticleDet?ID=477)
* [Using a UNIX/Linux emulator (Cygwin) or Secure Shell (SSH) client (Putty)](http://faculty.smu.edu/reynolds/unixtut/windows.html) 

### Manuals
* [GNU manuals](http://www.gnu.org/manual/manual.html)
* [Core GNU utilities](http://www.gnu.org/software/coreutils/manual/coreutils.html)

### UD Sites 
* [UD Service Portal](https://services.udel.edu/TDClient/32/Portal/Home/)
* [UD IT-RCI](https://sites.udel.edu/research-computing/)
* [UD IT-RCI HPC Documentation Wiki](https://sites.udel.edu/research-computing/)


### Text Editing

* [Nano editor home page](https://www.nano-editor.org/)

  * [Nano tutorial](https://www.howtoforge.com/linux-nano-command/)

* [VIM editor home page](https://www.vim.org/)

  * Vim also has a built-in tutorial. From the bash prompt, type `vimtutor`
    and follow the instructions.


