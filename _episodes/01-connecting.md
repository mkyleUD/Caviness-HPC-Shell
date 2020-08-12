---
title: "Connecting to the Caviness Cluster"
teaching: 20 
exercises: 10
questions:
- "How do I open a terminal?"
- "How do I connect to a remote computer?"
objectives:
- "Remotely connect to the Caviness Cluster"
keypoints:
- "Connect to the Caviness Cluster by using SSH: `ssh -Y yourUsername@caviness.hpc.udel.edu`"
---

## Opening a Terminal

Connecting to  {{ site.workshop_host }} must be done through a tool known as "SSH" (Secure SHell) and
usually it is run through a terminal. So, to begin using  {{ site.workshop_host }} we need to begin by opening
a terminal. Different operating systems have different terminals, none of which are exactly the same
in terms of their features and abilities while working on the local operating system. When connected to
the remote system the experience between terminals will be identical as each will faithfully present
the same experience of the  {{ site.workshop_host }}  Cluster.

Here is the process for opening a terminal in each operating system.

### Linux

There are many different versions (aka "flavors") of Linux and how to open a terminal window can
change between flavors. Fortunately, most Linux users already know how to open a terminal window
since it is a common part of the workflow for Linux users. If this is something that you do not know
how to do then a quick search on the Internet for "how to open a terminal window in" with your
particular Linux flavor appended to the end should quickly give you the directions you need.

A very popular version of Linux is Ubuntu. There are many ways to open a terminal window in Ubuntu
but a very fast way is to use the terminal shortcut key sequence:
<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>T</kbd>.

### Mac

Macs have had a terminal built in since the first version of OS X since it is
built on a UNIX-like operating system, leveraging many parts from BSD (Berkeley Systems Designs).
The terminal can be quickly opened through the use
of the Searchlight tool. Hold down the command key and press the spacebar. In the search bar that
shows up type "terminal", choose the terminal app from the list of results (it will look like a
tiny, black computer screen) and you will be presented with a terminal window. Alternatively, you
can find Terminal under "Utilities" in the Applications menu.

### Windows

While Windows does have a command-line interface known as the "Command Prompt" that has its roots in
MS-DOS (Microsoft Disk Operating System) its built-in SSH tool does not have all the options we
need in setting up our SSH connections. To get those additional options we will need to install 
some 3rd party applications. There are a variety of programs that can be used. Below we will go 
into the details of two more common ones.

#### PuTTY

It is strictly speaking not necessary to have a terminal running on your local computer in order to
access and use a remote system, only a window into the remote system once connected. PuTTy is likely
the oldest, most well-known, and widely used software solution to take this approach.


PuTTY is available for free download from 
[UDeploy](https://udeploy.udel.edu/software/putty-with-xming/) or 
[www.putty.org](http://www.putty.org/). Through the UDeploy site you will have the option to 
download and install Putty, Xming, and WinSCP. It is suggested that you download and install all
three of these programs. The download and installation process will not be covered in this lesson.
For directions on how to download, install, and set up  PuTTY can be found in the course's
[setup lesson]({{site.url}}{{site.baseurl}}/setup).

Running PuTTY will not initially produce a terminal but instead a window full of connection options.
Putting the address of the remote system in the "Host Name (or IP Address)" box and either pressing
enter or clicking the "Open" button should begin the connection process. If there is a save session
you could alternatively "double click" a on the saved session name, or click to highlight it and 
then click on the "Open" button to start the connection process.

If this works you will see a terminal window open that prompts you for a username through the "login
as:" prompt and then for a password. If both of these are passed correctly then you will be given
access to the system and will see a message saying so within the terminal. If you need to escape the
authentication process you can hold the Control (<kbd>ctrl</kbd>) key and press the <kbd>C</kbd> key
to exit and start again.

Note that you may want to paste in your password rather than typing it. Use <kbd>ctrl</kbd> plus a
right-click of the mouse or use <kbd>shift</kbd> + <kbd>insert</kbd> to paste content from the clipboard to the PuTTY terminal.

For those logging in with PuTTY it would likely be best to cover the terminal basics already
mentioned above before moving on to navigating the remote system.

#### XMing

Xming is an X11 display server for Microsoft Windows operating systems, for Windows XP and 
later. It can be installed to allow a GUI launched from  {{ site.workshop_host }} to display on your Windows
computer. This will allow you to interact with a program's GUI, such as Matlab, or view images of 
results such as charts or tables. The download and installation process will not be covered in this
lesson. For directions on how to download, install, and set up  XMing can be found in the course's
[setup lesson]({{site.url}}{{site.baseurl}}/setup).

[comment]: <>#### MobaXterm

[comment]: <> MobaXterm is a terminal window emulator for Windows and the home edition can be downloaded for free
[comment]: <> from [mobatek.net](https://mobaxterm.mobatek.net/download-home-edition.html). If you follow the link
[comment]: <> you will note that there are two editions of the home version available: Portable and Installer. The
[comment]: <> portable edition puts all MobaXterm content in a folder on the desktop (or anywhere else you would
[comment]: <> like it) so that it is easy add plug-ins or remove the software. The installer edition adds
[comment]: <> MobaXterm to your Windows installation and menu as any other program you might install.
[comment]: <> If you are not sure that you will continue to use MobaXterm in the future, the portable edition
[comment]: <> is likely the best choice for you.

[comment]: <> Download the version that you would like to use and install it as you would any other software on
[comment]: <> your Windows installation. Once the software is installed you can run it by either opening the
[comment]: <> folder installed with the portable edition and double-clicking on the executable file named
[comment]: <> `MobaXterm_Personal_11.1` (your version number may vary) or, if the installer edition was used,
[comment]: <> finding the executable through either the start menu or the Windows search option.

[comment]: <> Once the MobaXterm window is open you should see a large button in the middle of that window with
[comment]: <> the text \"Start Local Terminal\". Click this button and you will have a terminal window at your
[comment]: <> disposal.

[comment]: <> Details about installing a setting MobaXterm will not be covered in this workshop.

## Logging onto the system

With all of this in mind, let's make a remote connection. In this workshop, we will connect to
{{ site.workshop_host }} --- which is one of three community clusters at {{ site.workshop_host_location }}. Although it's unlikely
that every system will be exactly like {{ site.workshop_host }}, it's a very good example of what you can expect from
an HPC installation. To connect to our example computer, we will use SSH (if you are using
PuTTY, see above).

SSH allows us to connect to UNIX computers remotely, and use them as if they were our own. The
general syntax of the connection command follows the format `ssh yourUsername@some.computer.address`.
Let's attempt to connect to the HPC system now:

```
ssh yourUsername@{{ site.workshop_host_login }}
```
{: .language-bash}

```{.output}
{% include /snippets/01/login_output.{{ site.workshop_host_id }} %}
```

If you've connected successfully, you should see a prompt like the one below. This prompt is
informative, and lets you grasp certain information at a glance. (If you don't understand what these things are,
don't worry! We will cover things in depth as we explore the system further.)

```{.output}
{{ site.workshop_host_prompt }}
```
*Note that  {{ site.workshop_host }} has two login node `login00` and `login01`. The above output could reflect either node.*
## Telling the Difference between the Local Terminal and the Remote Terminal

You may have noticed that the prompt changed when you logged into the remote system using the
terminal (if you logged in using PuTTY this will not apply because it does not offer a local
terminal). This change is important because it makes it clear on which system the commands you type
will be run when you pass them into the terminal. This change is also a small complication that we
will need to navigate throughout the workshop. Exactly what is reported before the `$` in the
terminal when it is connected to the local system and the remote system will typically be different
for every user. We still need to indicate which system we are entering commands on though so we will
adopt the following convention:

- `[local]$` when the command is to be entered on a terminal connected to your local computer
- `{{ site.workshop_host_prompt }}` when the command is to be entered on a terminal connected to the remote system
- `$` when it really doesn't matter which system the terminal is connected to.

> ## Being certain which system your terminal is connected to
>
> If you ever need to be certain which system a terminal you are using is connected to then use the
> following command: `$ hostname`.
{: .callout}

> ## Keep two terminal windows open
>
> It is strongly recommended that you have two terminals open, one connected to the local system and
> one connected to the remote system, that you can switch back and forth between. If you only use
> one terminal window then you will need to reconnect to the remote system using one of the methods
> above when you see a change from `[local]$` to `{{ site.workshop_host_prompt }}` and disconnect when you see the
> reverse.
{: .callout}
{% include links.md %}
