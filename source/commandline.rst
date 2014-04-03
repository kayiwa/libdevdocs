===========
Commandline
===========

You may be asking yourself about the virtue using the Commandline. In many way the Graphic User Interface is friendlier. For many users it feels familiar and to other Operating Systems. The reason for learning the commandline is primarily a way to introduce you to what administering a server that could be in a remote location where you have no physical access. Your Ubuntu virtual machine is a good place to get practice. This segment is driven towards some repetitive exercises with a goal to make you comfortable on your Ubuntu virtual machine.

Navigation
==========

Location 
--------

We will start with the ``pwd`` which stands for Present Working Directory. Many of the commands in UNIX are often an abbreviation of a word of words describing what they do. 

.. code::
	
	username@hostname:~$ pwd
	/home/username
	username@hostname:~$

The command ``ls`` which is short for list will produce the following on your termimal

.. code::
	
	username@hostname:~$ ls
	Desktop Documents Downloads Music Pictures Public Templates Videos

Before we proceed much futher it is important to remember that all UNIX systems are designed with a built-in manual to explain what the commands do. The way to find out what it does is to prepend the command with ``man`` In the examples above it would be ``man pwd`` and ``man ls``. Go ahead and type those and read what the manual says about them. As you may have see the ``ls`` command can take arguments while the ``pwd`` does not. Below is an outline of the use of ``ls``.

.. code::
	
	ls [options][location]

The square brackets above are optional. Here are more examples.

.. code::

	username@hostname:~$ ls
	Desktop Documents Downloads Music Pictures Public Templates Videos
	username@hostname:~$ ls -l
	total 48
	drwxr-xr-x  3 fkayiwa fkayiwa 4096 Mar  7 14:09 Desktop
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Documents
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Downloads
	-rw-r--r--  1 fkayiwa fkayiwa 8445 Dec  9 17:21 examples.desktop
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Music
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Pictures
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Public
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Templates
	drwxr-xr-x  2 fkayiwa fkayiwa 4096 Dec  9 17:32 Videos
	username@hostname:~$ls -l /var
	total 52
	drwxrws---  5 archivematica archivematica 4096 Mar  6 11:38 archivematica
	drwxr-xr-x  2 root          root          4096 Apr  1 07:35 backups
	drwxr-xr-x 19 root          root          4096 Mar  6 11:10 cache
	drwxrwsrwt  2 root          whoopsie      4096 Dec 26 07:35 crash
	drwxr-xr-x  2 root          root          4096 Aug 20  2013 games
	drwxr-xr-x 68 root          root          4096 Mar  6 11:23 lib
	drwxrwsr-x  2 root          staff         4096 Dec 11 15:04 local
	lrwxrwxrwx  1 root          root             9 Mar 10 13:40 lock -> /run/lock
	drwxr-xr-x 24 root          root          4096 Apr  3 07:55 log
	drwxrwsr-x  2 root          mail          4096 Mar 31 07:58 mail
	drwxr-xr-x  2 root          root          4096 Aug 20  2013 opt
	lrwxrwxrwx  1 root          root             4 Mar 10 13:40 run -> /run
	drwxr-xr-x 10 root          root          4096 Mar  6 11:23 spool
	drwxrwxrwt  2 root          root          4096 Apr 19  2012 tmp
	drwxr-xr-x  2 root          root          4096 Dec 11 11:59 www




