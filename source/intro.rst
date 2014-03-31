============
Installation
============

In this chapter you will learn how to install a Virtual Machine (with Ubuntu operating system) and a Python interpreter on your Machine. The motivation for using a virtual machine is mostly for uniformity in the workshop. If you are attempting this workshop outside the classroom, this chapter (or at least the virtual machine part) may be optional. However keep in mind the rest of the workshop assumes you are using Ubuntu 12.04 LTS. 


On Windows
==========
Downloading VMWare Player and Ubuntu
------------------------------------
To get started, you'll need to download VMWare Player. You will need administrator privileges on your machine to install this!

1. Start by going to www.vmware.com/download/player

	1. The page will redirect - scroll down to VMWare Player and choose "Download Product." 
    2. Look for "VMWare Player and VMWare Player Plus for Windows" and choose "Download."
    3. Leave yourself some time, as it takes a while to download.

2. When the .exe file is done downloading, double-click it wherever you've saved it (probably your Downloads folder).

	1. A pop-up box will open that says "Do you want to run this file?" Click "Run."
    2. Accept the user agreement.
    3. A new window will pop up with an install sequence - you should be able to accept any defaults and go through the sequence quickly.

3. If VMWare Player doesn't open automatically, go into your Programs menu and open it.
4. You will now see a new window - at the top should be "Welcome to VMWare Player," and the first option beneath that should be "Create a New Virtual Machine." 

You can pause now in the process and move on to:

Downloading Ubuntu
------------------

1. Start by going to http://www.ubuntu.com/download/desktop and choose Ubuntu 12.04 LTS.

	1. Choose Ubuntu 12.04 LTS (there will be an option to select your operating system above the orange download button).
    2. This will take you to a page asking you to donate to Ubuntu. If you don't want to donate, you can scroll to the bottom for the "Not now, take me to the download" link.
	3. Your file should start downloading. Again, this can take a while to download, so leave yourself some time.

2. That's it! You're done.

Installing Ubuntu on your Virtual Machine
-----------------------------------------
Now we're starting to get to the fun part!

1. Go back to your VMWare Player window that says "Create a new Virtual Machine."
2. A second window should pop up which says "Welcome to the New Virtual Machine Wizard." It asks you how you will install the operating system.

	1. Choose the option "Installer disc image file (iso):"
    2. Browse to where you saved your Ubuntu file (probably your Downloads folder) and choose that file ("ubuntu-12.04.4-desktop-amd64.iso")
    3. Click "Next"

3. You will move on to "Easy Install Information"

	1. Set your name as it will display under Full name
	2. Set a name for your username 
	3. Set a name for your password
	4. Click "Next"

4. Give your virtual machine a name (maybe something like "PythonClass").
5. Accept the default location and click "Next."
6. It will ask you about the disk capacity - maximum size and whether or not to split the virtual disk into multiple files. Accept the defaults and click "Next."
7. Click "Finish" - the virtual machine should start up once you do.

*Important Note:
We are going to be using the command line to do this next part. If your Ubuntu VM has defaulted to opening in the command line (you will see a black screen with a white blinking cursor waiting for your commands), proceed right away. If, on the other hand, your Ubuntu VM has defaulted to a normal-looking desktop interface, type CTRL-ALT-F1 to switch to the command line.
To use your VM with command line, just click in the window. To get your mouse back so you can do anything else, type CTRL-ALT.*

Installing ssh-server
---------------------
Now we're really getting somewhere. 

1. In your command-line interface, type: ``sudo apt-get install openssh-server``
2. Type in your password.
3. After a little thinking, your machine should tell you how much space the installation will take, and ask you if you want to proceed. Type: y
4. Hit the 'Enter' key.
 
Getting ready with Python
-------------------------
To double-check that Python is installed on your machine (it should come with your installation of Ubuntu), type: python --version
You should get back something like: Python 2.7.3
 
**If Python is not installed:**
1. Type: ``sudo apt-get install python2.7``
2. It will ask for your password - type that in.
3. It should tell you how much disc space nano will take, and ask if you're sure you want to install (Y/n). Type: y
4. Hit the 'Enter' key.
5. You should be done! You can check that it installed properly by typing: python --version
 
Installing the nano text editor
-------------------------------
Python is already installed on your machine, but your machine will still need a way to write Python programs, and help figuring out what to *do* with them. Luckily, your ubuntu VM should also come with nano, which is a text editor that can write Python. To double-check that Python is installed on your machine, type: nano --version 
You should get back something like: GNU nano version 2.2.6 (compiled 20:32:12, Dec 3 2010) ...
 
**If nano is not installed:**
1. Type: ``sudo apt-get install nano``
2. It will ask for your password - type that in.
3. It should tell you how much disc space nano will take, and ask if you're sure you want to install (Y/n). Type: y
4. Hit the 'Enter' key.
5. You should be done! You can check that it installed properly by typing: nano --version

Congratulations! You are now officially ready to roll!

On Mac OSX
============
Downloading VMWare Fusion and Ubuntu
------------------------------------
To get started, you'll need to download VMWare Fusion. You will need administrator privileges on your machine to install this! 

1. Start by going to www.vmware.com/products/fusion and choose "Download Free Trial" - you'll get 30 days of free access.
	1. Leave yourself some time, as it takes a while to download.
2. When the file is done downloading, click on the .dmg file.
	1. A pop-up box will open that says "Double-click to Install" - do it!
    2. Accept the user agreement.
    3. Since you won't have a product key, choose the free 30-day trial option.
    4. Put in your email address to continue (it doesn't look like there's a way around this, unfortunately).
    5. This finishes the VMWare Fusion download and install process.
    6. You'll see a new box pop up called "New Virtual Machine."  

You can pause now in the process and move on to:

Downloading Ubuntu
------------------

1. Start by going to http://www.ubuntu.com/download/desktop and choose Ubuntu 12.04 LTS.

	1. Choose Ubuntu 12.04 LTS (there will be an option to select your operating system above the orange download button).
    2. This will take you to a page asking you to donate to Ubuntu. If you don't want to donate, you can scroll to the bottom for the "Not now, take me to the download" link.
	3. Your file should start downloading. Again, this can take a while to download, so leave yourself some time.

2. That's it! You're done.

Installing Ubuntu on your Virtual Machine
-----------------------------------------
We're starting to get to the fun part!

1. Go back to your VMWare Fusion window that says "Create a Virtual Machine."
2. The window should say "Select the Installation Method."
3. Make sure the "Install form disc or image" option is selected, and then click "Continue."
4. You should come to a new window which says, "Choose an operating system installation disc or image:" over a box which will be blank.

	1. Choose the button toward the bottom, "Use another disc or disc image."
    2. In the window that pops up, browse to wherever you saved the Ubuntu file you just downloaded (for me, it's my downloads folder).
    3. Find the file "ubuntu-12.04.4-desktop-amd64.iso" and choose "Open."
    4. Ubuntu should now be listed as an option and selected in the window under "Choose an operating system installation disc or image."
    5. Choose "Continue."
    6. Choose "Easy Install."

    	1. Set your name as it will display.
        2. Set a name for your username (Account Name).
        3. Set a password.
        4. Make sure the drop-down menu at the bottom says "The virtual machine can: Read & Write."
        
     7. Click "Continue."
     8. Double-check your settings and click "Finish."

*Important Note:
We are going to be using the command line to do this next part. If your Ubuntu VM has defaulted to opening in the command line (you will see a black screen with a white blinking cursor waiting for your commands), proceed right away. If, on the other hand, your Ubuntu VM has defaulted to a normal-looking desktop interface, click on the 'Dash Home' button at the top left of your screen and search for Terminal. Open Terminal and then proceed with the directions.*

Installing ssh-server
---------------------
Now we're really getting somewhere. 

1. In your command-line interface, type: ``sudo apt-get install openssh-server``
2. Type in your password.
3. After a little thinking, your machine should tell you how much space the installation will take, and ask you if you want to proceed. Type: y
4. Hit the 'Enter' key.

Getting ready with Python
-------------------------
To double-check that Python is installed on your machine (it should come with your installation of Ubuntu), type: python --version
You should get back something like: Python 2.7.3

**If Python is not installed:**
1. Type: ``sudo apt-get install python2.7``
2. It will ask for your password - type that in.
3. It should tell you how much disc space nano will take, and ask if you're sure you want to install (Y/n). Type: y
4. Hit the 'Enter' key.
5. You should be done! You can check that it installed properly by typing: python --version

Installing the nano text editor
-------------------------------
Python is already installed on your machine, but your machine will still need a way to write Python programs, and help figuring out what to *do* with them. Luckily, your ubuntu VM should also come with nano, which is a text editor that can write Python. To double-check that Python is installed on your machine, type: nano --version 
You should get back something like: GNU nano version 2.2.6 (compiled 20:32:12, Dec 3 2010) ...

**If nano is not installed:**
1. Type: ``sudo apt-get install nano``
2. It will ask for your password - type that in.
3. It should tell you how much disc space nano will take, and ask if you're sure you want to install (Y/n). Type: y
4. Hit the 'Enter' key.
5. You should be done! You can check that it installed properly by typing: nano --version
Congratulations! You are now officially ready to roll!

=================
Post Installation
=================

In the next section we will focus on connecting to your new Virtual Machine from the host computer. If your host computer is the Windows you will need to install the Putty application. If your host computer is a Mac you will can use the Terminal Application. 

The Terminal Applications is found in the Utilities Directory under the Applications directory of all Mac OSX versions. Launch the Terminal application by double clicking and skip the next section.


Installing Putty
----------------

If you don't already have it putty can be installed by downloading the software from `the Putty Homepage <http://www.chiark.greenend.org.uk/~sgtatham/putty/>` 

1. Download and run the current setup executable.
2. The default installation location is recommended
3. The Start Menu folder is simply the name of the sub directory under which your PuTTY shortcuts will be located. The default value should be fine.

Launch the Putty application and follow the steps in the next section.

