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
