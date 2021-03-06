---
layout: page
title: Setup
permalink: /setup/
---

As stated in the prerequisites, below is an explanation of how to install the required software needed prior to starting the workshop.

## SSH

All students should have an SSH client installed.
SSH is a tool that allows us to connect to and use a remote computer as our own.
Please follow the directions below to install an SSH client for your system.

### Linux

Linux users do not need to install anything, you should be set!

### macOS 

Although macOS comes with SSH pre-installed, 
you will likely want to install [XQuartz](www.xquartz.org) to enable graphical support
(Also known as X11 or Xwin). Graphical support allows you to interact with a programs
graphical user interface (GUI) and view images.

***Note:*** You must restart your computer to complete the installation.


### Windows

PuTTY is used to create a command line interface (CLI) on a remote system from machines running 
a Windows operating system. Unlike Linux/UNIX and Mac, Windows does not have a native terminal
that has an SSH client installed by default. While this is changing in newer versions of Windows,
we are suggesting that all Windows users install and use PuTTY. 

**Download PuTTY** from [UDeploy](https://udeploy.udel.edu/software/putty-with-xming/).
You might also want to download WinSCP, but it will not be needed for the workshop or covered in this setup.

**Install PuTTY**
***Note:*** This will require administrator privileges on your computer .
 
 * **Step 1:** Run the putty-X.XX-install.msi file that was downloaded to begin the installation 
 process. Click "Next".

 ![PuTTY Install Wizard](/fig/step1Welcome.jpg)
 
 [comment]: <> ![PuTTY Install Wizard](/fig/step1Welcome.jpg) 
 
 * **Step 2:** Use the default folder path destination. Click "Next".

![PuTTY Install Wizard](/fig/step2FolderPath.jpg)  

 * **Step 3:** Click "Install". 
 
![PuTTY Install](/fig/step3install.jpg) 

 * **Step 4:** Click "Finish". 

![Finish PuTTY Install](/fig/step4Finish.jpg) 

 * **Step 5:** Use the Windows Start to search for and start PuTTY.
 
 ![PuTTY Install](/fig/step5StartPuTTY.jpg) 

 * **Step 6:** With the "Session" Category Selected, click on the Host Name (or IP address) text 
 box. Type ***caviness.hpc.udel.edu***. Then click on the Saved Sessions text box. Type "caviness".
 
 ![PuTTY Install](/fig/step6Session.jpg) 
 
 * **Step 7:** Click on the "Data" sub category under the Connection category. In the Auto-login username text box enter your UDelNet 
 ID. In Terminal-type string text box type "xterm-color".
 
 ![PuTTY Install](/fig/step7Data.jpg) 
 
 * **Step 8:** Click on the "SSH" sub category under the Connection category and then the "X11" sub category. Check the box "Enable
X11 forwarding" 

 ![PuTTY Install](/fig/step8X11.jpg) 
 
 * **Step 9:** Click on the "Session" category again. Then click the "Save" button. This will save 
all the changed settings made in a saved session called "caviness" in the Saved Sessions text box.
 
 ![PuTTY Install](/fig/step9SavedSession.jpg) 
 
 * **Step 10:** To open a PuTTY terminal to Caviness, click "caviness" to highlight it then click 
 "Open". 
 
 ![PuTTY Install](/fig/step10openTerminal.jpg) 
 
 * **10 a:** If it is your first time logging on to Caviness Click "Yes" to the PuTTY Security 
 Alert. This should only happen the first time your log on to a new server.
 
 ![PuTTY Install](/fig/First_Caviness_Logon.jpg) 
 
 * **11:** The last step to starting your terminal session will be to enter your UDelNet username
 password. As you type it, be careful as you will not see what you type on your screen. 
 
 ![PuTTY Install](/fig/step11LoggedOn.jpg) 
 
 
**Download Xming and Xming-fonts** from [sourceForge](https://sourceforge.net/projects/xming/files/).


Xming is used to enable graphical support (Also known as X11 or Xwin). Graphical support allows 
you to interact with a programs graphical user interface (GUI) and view images. 

**Install XMing** 

***Note:*** This will require administrator privileges on your computer .
 
 * **Step 1:** Run the Xming-X-X-X-X-setup.exe file that was download to begin the installation 
 process. Click "Next".

![X Ming Install Wizard](/fig/step1_X_Welcome.jpg) 
 
 * **Step 2:** Use the default folder path destination. Click "Next".

![X Ming Install Wizard](/fig/step2_X_FolderPath.jpg)  

 * **Step 3:** Change "Normal PuTTy Link SSH client" to "Don't install an SSH client".  Then click 
 "Next". If asked about existing programs click on "Yes".
 
 
![X Ming Install](/fig/step3_X_components.jpg) 

 * **Step 4:** Click "Next".
  
 
![X Ming Install](/fig/step4_X_Folder.jpg) 

 * **Step 5:** Click "Next".
  
 
![X Ming Install](/fig/step5_X_tasks.jpg) 

 * **Step 6:** Click "Install".
  
 
![X Ming Install](/fig/step6_X_install.jpg)
 
 * **Step 6a:** Click "Allow Access".
  
 
![X Ming Install](/fig/step6a_X_firewall.jpg)

**Install XMing fonts** 

***Note:*** This will require administrator privileges on your computer .

 * **Directions** :The default setting for the X Ming fonts are all correct. Simply start the 
installation process and click "Next" or "Yes" till the final step of the Setup Wizard, then
click "Install". 

**Alternative Directions:**
For an alternative set of directons on how to install PuTTY and XMING vist University of Delaware's
service page on [Using X-Windows(X11) and secure shell(SSH) to connect to a remote UNIX Server(host)](https://services.udel.edu/TDClient/32/Portal/KB/ArticleDet?ID=491)
. You can also email  [askit@udel.edu](mailto:askit@udel.edu) if you have issues with the installation.

