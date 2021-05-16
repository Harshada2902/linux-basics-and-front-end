## User and Groups

#### Adding a User
If you are signed in as the root user, you can create a new user at any time by typing:

######  # adduser newusername

If you are signed in as a non-root user who has been given sudo privileges, you can add a new user by typing:

######  $ sudo adduser newusername

Assign and confirm a password for the new user

#### Adding the New User to the Sudo Group
By default, <b>sudo</b> on Ubuntu 18.04 systems is configured to extend full privileges to any user in the sudo group.

You can see what groups your new user is in with the <b>groups</b> command:
###### $ groups user1

OUTPUT: 
###### user1 : user1

#### Deleting a User
You can delete the user itself, without deleting any of their files, by typing the following command as <b>root</b> :
###### # deluser user1 
or with sudo , type:

###### $ sudo deluser user1

 ##### Note:
  you can use <b>sudo -i</b> to switch between users.
  
  
 #### Create a User Group
 
 To create a new group, enter the following:
 ###### sudo groupadd new_group
 Use the adduser command to add an existing  user to an existing group:
 ###### sudo adduser user_name new_group
 use the useradd command to add a user to a group:
 ###### sudo useradd –G new_group user_name
 
##### Create a User and Add to Group:

###### sudo useradd –G new_group new_user

Next, assign a password to the new user:
###### sudo passwd new_user

The gpasswd tool is used for managing groups. 

To <b>remove</b> a user from a group:
###### sudo gpasswd –d user_name new_group

##### Delete a Group

To delete a group, use the command:
###### sudo groupdel new_group

<b>To display</b> the groups that a user belongs to with the groups command:
###### groups

You can display groups for a different user by specifying the username:
###### groups other_user
or you can list all groups by

###### $ cat /etc/group

##### Set or change password for user
######  # passswd username









 
 
 
 
 
  







