### Softlink
A symbolic or soft link is an actual link to the original file.
If you delete the original file, the soft link has no value, because it points to a non-existent file. 
    1. It has different inode number and file permissions than original file.
    2. It has only path of the original file

### Hardlink
 In the case of hard link, it is entirely opposite. 
 Even if you delete the original file, the hard link will still has the data of the original file.  Because hard link acts as a mirror copy of the original file.
      1. It has the same inode number and permissions of original file. 
      2. It has the actual contents of original file, so that you still can view the contents, even if the original file moved or removed.

#### Creating Soft Link
create a text file using vi or nano. for ex <b>soft</b>
 Now, create the a symbolic or soft link to the soft file
 
###### $ ln -s soft.txt softlink.file



As you see in the above output, softlink displays the same data as soft.
check the inodes and permissions of both files.
type 
###### ls -lia
 Now remove the file and cjheck content using softlink.
 
 
 
 As you see above, there is no such file or directory called softlink after we removed the original file .
 
 #### Creating Hard Link
type  
 ###### $ ln hard hardlink
 Check the inode and permissions of hard and hardlink.
 
 
 
 As you see above, even if I deleted the source file, I can view contents of the hardlink file. 
 Hence, it is proved that Hard link shares the same inode number, the permissions and data of the original file.
 
If you copy a file, it will just duplicate the content. So if you modify the content of a one file (either original or hard link), it has no effect on the other one. 
However if you create a hard link to a file and change the content of either of the files, the change will be be seen on both.
so creating hardlink is different than copying.
