===================
Ubuntu Introduction
===================

We now have a Virtual Machine set up. In this section we will work on connecting to the Virtual Machine from the host computer. 

The steps for this require us to log in and work from the Virtual Machine one "last" time. So if your Virtual Machine is not running please follow the platform specific steps below to start the Virtual Machine. 

On Windows
==========

Start the VMWare Player Application and double click on the Ubuntu Virtual Machine you created in the last section. 

On Mac OSX
==========

Start the VMWare Fusion Application and double click the Ubuntu Virtual Machine you created in the last section.

Get IP address of Virtual Machine
---------------------------------

We will log into the virtual machine by using the username created in the previous section. This will be followed by launching Terminal. The way to do this is to click the Dash at the top left of your Desktop. Search for Terminal and start the application.

From within the Terminal type ``ifconfig``

.. code:: 

    eth0    Link encap:Ethernet  HWaddr 00:26:bb:53:8d:90
            inet addr:192.168.0.14  Bcast:192.168.0.255  Mask:255.255.255.0
                

From the results we are interested in the numbers after inet addr in the eth0 device. This is the IP address of your Virtual Machine. Write this down for future use. In the fake example above the IP address of our Virtual Machine is 192.168.0.14. 

Connecting from Windows
-----------------------

For the rest of the tutorial these will be the steps used to connect to your Virtual Machine. Enter the IP address in the step above and click on the Open. On your first connection you will get a pop up key warning you about the fingerprint of the server you are about to connect to. Accept the keys and enter your username and password in the window that follows. 


Connecting from Mac OSX
-----------------------

For the rest of the tutorial these will be the steps used to connect to your Virtual Machine. Type the following in your Terminal.app (this was the last step in the last segment) ``ssh -l username IP Address`` So if your username was jondoe on my fake Virtual Machine above the steps would be ``ssh -l jondoe 192.168.0.14`` On your first connection you will get a warning about the fingerprint of the server you are about to connect to. Accept the keys and enter your password.

Administration Basics
=====================

On your first log in it is possible that you will see a message resembling the one I saw while creating this tutorial.

.. code::

	88 packages can be updated.
	80 updates are security updates

It is extremely important to heed this advice. Even though you are running a virtual machine (incidentally this is the reason for lagging behind) it is important to get into good administration habits early. The way to fix this is to type the following.

.. code::

	sudo apt-get update        # Fetches the list of available updates from the Ubuntu project
	sudo apt-get upgrade	   # Upgrades your Ubuntu virtual machine

In the next segment we will get more comfortable with general computation from the commandline. To logout of your virtual machine type ``exit`` . You can then shutdown your VMWare Player Application or VM Fusion application.