# File Permissions
#### File and Directory permissions
To check the permission configuration of a file, use the command:
###### ls –l [file_name]
For instance, the command for the "test.txt" file would be:
###### ls –l test.txt

The output provides the following information:

  1. file permission
  
  2. the owner (creator) of the file
  
  3. the group to which that owner belongs to
  
  4. the date of creation.
   
   
   It shows the permission settings, grouped in a string of characters <b>(-, r, w, x)</b> classified into four sections:

   File type. There are three possibilities for the type. It can either be a regular file (–), a directory (d) or a link (i).
   1. File permission of the user (owner)
   
   2. File permission of the owner’s group
   
   3. File permission of other users

The characters r, w, and x stand for <b>read, write, and execute.</b>

Users that have reading permission can see the content of a file (or files in a directory). 

However, they cannot modify it (nor add/remove files in a directory).

On the other hand, those who have writing privileges can edit (add and remove) files. Finally, being able to execute means the user can run the file. This option is mainly used for running scripts.


#### Using Chmod Command to Change File Permissions 

###### chmod [permission] [file_name]
   
   <b>r</b>(ead) has the value of 4
   
  <b> w</b>(rite) has the value of 2
   
   (e)<b>x</b>(ecute) has the value of 1
   
   <b>no permission</b> has the value of 0
   
 ##### Total count for permissions
   
   7 – for read, write, and execute permission
   
   6 – for read and write privileges
   
   5 – for read and execute privileges
   
   4 – for read privileges
   
   
#### Define File Permission with Symbolic Mode

To specify permission settings using alphanumerical characters, you’ll need to define accessibility for the user/owner<b> (u)</b>, group <b>(g)</b>, and others <b> (o)</b>.

To set a file, so it is public for reading, writing, and executing, the command is:
###### chmod u=rwx,g=rwx,o=rwx [file_name]
for ex:
###### chmod u=rw,g=r,o=r test.txt

The same permission settings can be defined using the octal format with the command:

###### chmod 644 test.txt

#### Changing User File and Group Ownership
To change the file ownership use the chown command:
###### chown [user_name] [file_name]

To change the group ownership type in the following command:
###### chgrp [group_name] [file_name]
   
   



