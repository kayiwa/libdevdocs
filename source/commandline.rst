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

The square brackets above are optional. Here is an example with the echo of the results shown.

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

So what did we just do? 

* The ``ls`` will list the contents of our current directory.
* The ``ls -l`` adds the optional switch ( -l)  to do the long listing. A long listing has the following:
	
	* First character indicates whether it is a normal file ( - ) or directory ( d )
	* Next 9 characters are permissions for the file or directory (we'll learn more about them in a later segment)
	* The next file is the number of blocks.
	* The next field is the owner of the file or directory (fkayiwa/root in the examples above).
	* The next field is the group the file or directory belongs to (fkayiwa).
	* Following this is the file size.
	* Next up is the file modification time.
	* The actual name of the file or directory.

Here is another example.

.. code::

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

* We ran ``ls`` with a command line argument ( /var ). When we do this it tells ``ls`` not to list our current directory but instead to list that directories contents.

Spend a little time perusing the ``ls`` manual by doing the following. ``man ls``

Paths
-----

The previous section touched on something about navigating your Ubuntu machine, namely the paths on the operating system. Understanding paths is essential in using your new computer. Whenever we refer to a file or directory on the command line we are in fact referring to the actual path to it.

Referring to paths can be done using the absolute path or a relative path. 

At the top of the unix system is what is called the root directory. It is denoted by a single dash (/). It has sub-directories which have other sub-directories contained within them. Files can reside in any of these directories. 

Absolute paths refer to the location relative to the root directory. Relative paths specify location based on your current working directory. The example below will illustrate what we mean.

.. code::

    username@hostname:~$ pwd
    /home/fkayiwa
    username@hostname:~$
    username@hostname: ls Desktop
    test.mrc
    username@hostname:~$ ls /home/fkayiwa/Desktop
    test.mrc
    username@hostname:~$

So what just happened?

* We ran ``pwd`` to verify where we were on the filesystem.
* We ran ``ls`` providing it with a relative path. Desktop is a directory in our current location. We would get different results depending on where we are. 
* We finally ran ``ls`` providing and absolute path. This will provide the same output regardless of the location we ran it from.

Here are a few more tips that can help build on your new knowledge on paths. 

* ~ (tilde) - This is a shortcut for your home directory. So if the user fkayiwa above wanted to head to their home directory. Typing ~/Desktop in the example above is the equivalent of typing /home/fkayiwa/Desktop
* . (dot) - This is a reference to your current directory. We will see more on this later.
* . . (dotdot) - This is a reference to the parent directory. You can use this several times to keep going up the heirarchy.

A few more examples to explain this.

.. code::
        
    username@hostname:~$ pwd
    /home/fkayiwa
    username@hostname:~$
    username@hostname:~$ ls ~/Desktop
    test.mrc
    usename@hostname:~$ ls ./Desktop
    test.mrc
    username@hostname:~$ ls /home/fkayiwa/Desktop
    test.mrc
    username@hostname:~$ ls ../../
    bin boot lib lost+found proc selinux usr boot home lib32
    ...
    username@hostname:~$ ls /
    bin boot lib lost+found proc selinux usr boot home lib32
    ...

Spend time listing the content of various directories on your filesystem and familiarize yourself on how the elements of building a path. 

Moving around your filesystem
-----------------------------

In order to move around your filesystem we use the ``cd`` command which stands for change directory. 

A handy tip to remember is if you run the command ``cd`` without any arguments then it will always take you back to your home directory.

Otherwise the ``cd`` command can be used much like the ``ls`` before to change into absolute or relative paths as some of the examples below will show.

.. code::

    username@hostname:~$ pwd
    /home/fkayiwa
    username@hostname:~$ cd Desktop
    username@hostname:~$ ls
    test.mrc
    username@hostname:~$ cd /
    username@hostname:~$ pwd
    /
    username@hostname:~$ ls 
    bin boot lib lost+found proc selinux usr boot home lib32
    ...
    username@hostname:~$ cd ~/Desktop
    username@hostname:~$ pwd
    /home/fkayiwa/Desktop
    username@hostname:~$ cd ../../
    username@hostname:~$ pwd
    /home
    username@hostname:~$ cd
    username@hostname:~$ pwd
    /home/fkayiwa

Another handy tip when navigating is Tab Completion. Typing out these paths can become tedious. If you're like me, you're also prone to making typos. The command line has a nice little mechanism to help us in this respect. It's called Tab Completion.

When you start typing a path (anywhere on the command line, you're not just limited to certain commands) you may hit the Tab key on your keyboard at any time which will invoke an auto complete action. If nothing happens then that means there are several possibilities. If you hit Tab again it will show you those possibilities. You may then continue typing and hit Tab again and it will again try to auto complete for you.

It's kinda hard to demonstrate here so it's probably best if you try it yourself. If you start typing cd /hTab/<beginning of your username>Tab you'll get a feel for how it works.

Summary
-------

Commands we learned about

.. code::

    pwd - Present Working Directory
    ls - List the contents of a directory
    cd - Change directories


