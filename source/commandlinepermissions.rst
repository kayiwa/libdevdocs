=========================
Command Line: Permissions
=========================

We have not properly discussed permissions on your Linux files and directories. Permissions specify what a user may or may not do with respect to a file or directory. As such, permissions are important in maintaining the integrity of your computing. For instance you don't want other users to be changing your files and you also want system files to be safe from damage (either accidental or deliberate). Permissions in a Linux system are quite easy to work with.

Permissions dictate 3 things you may do with a file, read, write and execute. They are referred to in Linux by a single letter each.

    * r read - user may view the contents of the file
    * w write - user may change the contents of the file
    * x execute - user may execute or run the file as a program of script

For every file we define 3 sets of people for whom we may specify permissions.

    * owner - user owns the file. (typically the user who created the file but ownership may be granted to other users)
    * group - every file belongs to the single group
    * others - everyone else who is not in the group or owner

Three persmissions and three groups of people. That's about all there is to permissions really. Now let's see how we can view and change them.

View Permissions
----------------

To view permissions for a file we use the long listing option for the command ls.

.. code::

    ls -l [path]

.. code::

    username@hostname:~$ ls -l /home/fkayiwa/Desktop/test.mrc
    -rw-r--r-- 1 fkayiwa fkayiwa 1170 Mar 27 16:25 /home/fkayiwa/Desktop/test.mrc

In the above example the first 10 characters of the output are what we look at to identify permissions.

    * The first character identifies the file type. If it is a dash ( - ) then it is a normal file. If it is a d then it is a directory.
    * The following 3 characters represent the persmissions for the owner. A letter represents the presence of a permission and a dash ( - ) represents the absence of a permission. In this example the owner has all permissions (read, write and execute).
    * The following 3 characters represent the permissions for the group. In this example the group has the ability to read but not write or execute. Note that the order of permissions is always read, then write then execute.
    * Finally the last 3 characters represent the permissions for others (or everyone else). In this example they have the execute permission and nothing else.

Change Permissions
------------------




