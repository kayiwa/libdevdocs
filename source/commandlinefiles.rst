Command Line: Files
===================

Everything is a File
--------------------

Ok, the first thing we need to appreciate with linux is that under the hood, everything is actually a file. A text file is a file, a directory is a file, your keyboard is a file, your monitor is a file etc. Understanding this about Linux will make managing of these files and directories much easier to understand. 

Another key point to remember is that Linux has no extensions to identify what a file will do. This one can sometimes be hard to get your head around but as you work through the sections it will start to make more sense. A file extension is normally a set of 2 - 4 characters after a full stop at the end of a file, which denotes what type of file it is. The following are common extensions in the Microsoft Windows Operating systems:

	* file.exe - an executable file, or program.
	* file.txt - a plain text file.
	* file.png, file.gif, file.jpg - an image.

Under Linux the system actually ignores the extension and looks inside the file to determine what type of file it is. So for instance I could have a file myself.png which is a picture of me. I could rename the file to myself.txt or just myself and Linux would still happily treat the file as an image file. As such it can sometimes be hard to know for certain what type of file a particular file is. Luckily there is a command called ``file`` which we can use to find this out.

.. code::
	
	file [path]

The command above will provide you information about the file or directory (a special kind of file really)

Linux is Case Sensitive
-----------------------

In order to explain this let's take a slight detour.

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ touch Desktop/file1.txt

Before proceeding take time to look at the manual on the command ``touch`` and ``file``. In fact from here on every time you encounter a new command spend a few minutes reading up the manual on a more detailed account of what the command does.

On Microsoft Windows Operating systems it is possible to have two or more files and directories with the same name but letters of different case.

.. code::

	username@hostname:~$ ls Desktop
	test.mrc file1.txt
	username@hostname:~$ file Desktop/file1.txt
	/home/fkayiwa/Desktop/file1.txt: empty
	username@hostname:~$ file Desktop/FILE1.TXT
	/home/fkayiwa/FILE1.TXT: ERROR: cannot open `/home/fkayiwa/Desktop/FILE1.TXT' (No such file or directory)

Linux sees these all as distinct and separate files.

Also be aware of case sensitivity when dealing with command line options. For instance with the command ``ls`` there are two options s and S both of which do different things. A common mistake is to see an option which is upper case but enter it as lower case and wonder why the output doesn't match your expectation.

Spaces in names
---------------

Spaces in file and directory names are perfectly valid but we need to be a little careful with them. As you would remember, a space on the command line is how we seperate items. They are how we know what is the program name and can identify each command line argument. If we wanted to move into a directory called MARC Records for example the following would not work.

.. code::

	username@hostname:~$ ls Desktop
	test.mrc file1.txt
	username@hostname:~$ cd MARC Records
	-bash: cd: MARC: No such file or directory

What happens is that MARC Records is seen as two command line arguments. cd moves into whichever directory is specified by the first command line argument only. To get around this we need to identify to the terminal that we wish MARC Records to be seen as a single command line argument. There are two ways to go about this, either way is just as valid. (details on how to create this are in the next section)

The first approach invovles using quotes around the entire item. You may use either single or double quotes (later on we will see that there is a subtle difference between the two but for now that difference is not a problem). Anything inside quotes is considered a single item.

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ cd Desktop/'MARC Records'
	username@hostname:~$ pwd
	username@hostname:~$ /home/fkayiwa/Desktop/MARC Records

Another method is to use what is called an escape character, which is a backslash ( \ ). What the backslash does is escape (or nullify) the special meaning of the next character.

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ cd Desktop/MARC\ Records
	username@hostname:~$ pwd
	username@hostname:~$ /home/fkayiwa/Desktop/MARC Records

In the above example the space between MARC and Records would normally have a special meaning which is to separate them as distinct command line arguments. Because we placed a bashslash in front of it, that special meaning was removed.

Making a Directory
==================

Linux organises it's file system in a heirarchical way. Over time you'll tend to build up a fair amount of data (storage capacities are always increasing). It's important that we create a directory structure that will help us organise that data in a manageable way. I've seen way too many people just dump everything directly at the base of their home directory and waste a lot of their time trying to find what they are after amongst 100's (or even 1000's) of other files. Develop the habit of organising your stuff into an elegant file structure now and you will thank yourself for years to come.

Creating a directory is pretty easy. The command we are after is mkdir which is short for Make Directory.

.. code::

	mkdir [options] <Directory>

In it's most basic form we can run ``mkdir`` supplying only a directory and it will create one.

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ ls
	Desktop Documents Downloads Music Pictures Public Templates Videos
	username@hostname:~$ mkdir libdevops
	username@hostname:~$ ls
	Desktop Documents Downloads Music libdevops Pictures Public Templates Videos

So what happened here? 

	* Let's start off by making sure we are in the home directory
	* We'll do a listing so we know what is already in our directory.
	* Run the command mkdir and create a directory libdevops 

Remember that when we supply a directory in the above command we are actually supplying a path. Is the path we specified relative or absolute? Here are a few more examples of how we can supply a directory to be created

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ mkdir /home/fkayiwa/foo
	username@hostname:~$ mkdir ./bar
	username@hostname:~$ cd Desktop
	username@hostname:~$ mkdir ../dir1
	username@hostname:~$ mkdir ~/libdevops/dir2

If these don't make sense then review the section on Files.

There are a few useful options available for ``mkdir``. Spend some time on the manual to find out which. I will look at two that I've used quite a bit over the years. 

The first one is -p which tells mkdir to make parent directories as needed (demonstration of what that actually means below). The second one is -v which makes mkdir tell us what it is doing (as you saw in the example above, it normally does not).

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ mkdir ~/libdevops/foo/bar
	username@hostname:~$ cd ~/libdevops/foo/bar
	username@hostname:~$ pwd
	/home/fkayiwa/libdevops/foo/bar

And now the same command but with the -v option

.. code::

	username@hostname:~$ cd ~
	username@hostname:~$ mkdir -pv ~/libdevops/foo/bar/foo
	mkdir: created directory `/home/fkayiwa/libdevops/foo/bar/foo'

Removing a Directory
====================

Creating a directory is pretty easy. Removing or deleting a directory is easy too. One thing to note, however, is that there is no undo when it comes to the command line on Linux so some care will have to be exercised when using this. The command to remove a directory is ``rmdir`` , short for remove directory.

.. code::

	rmdir [options] <Directory>

Two things to keep in mind. Firstly, rmdir supports the -v and -p options similar to mkdir. Secondly, a directory must be empty before it may be removed (later on we'll see a way to get around this).

Copying a File or Directory
===========================

There are many reasons why we may want to make a duplicate of a file or directory. Often before changing something, we may wish to create a duplicate so that if something goes wrong we can easily revert back to the original. The command we use for this is ``cp`` which stands for copy.

.. code::

	cp [options] <source> <destination>

There are numerous options available to cp. As always check the manual. I will introduce some that I have used frequently over the years.

.. code::

	username@hostname:~$ cd ~/libdevops
	username@hostname:~$ touch example1 foo
	username@hostname:~$ cp example1 dewey
	username@hostname:~$ ls 
	dewey example1 foo

Note that both the source and destination are paths. This means we may refer to them using both absolute and relative paths.

