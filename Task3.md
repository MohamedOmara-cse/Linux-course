

### Create a user account 
with the following attribute
  - username: islam
  - Fullname/comment: Islam Askar
  - Password: islam
  
  ```
  sudo useradd -md  islam -c "Islam Asker"  -s /bin/bash islam
  sudo passwd islam 
  ```
  with the following attribute 
  
  - Username: baduser 
  - Full name/comment: Bad User 
  - Password: baduser 

  
  ```
  sudo useradd -md baduser -c "Bad User" -s /bin/bash
  sudo passwd baduser 
  ```
  
-------------------  
### Create a supplementary (Secondary) group
* called pgroup with group ID of 30000

```
sudo groupadd -g 30000 pgroup 
```

* called badgroup

```
sudo groupadd badgroup 
```

--------------------
### Add islam user to the pgroup group as a supplementary group

```
sudo usermod -G pgroup islam  
```
--------------------
### Modify the password of islam's account to password

```
sudo passwd islam
```
--------------------
### Modify islam's account so the password expires after 30 days

```
sudo chage islam -m 30
```
--------------------
###  Lock bad user account so he can't log in

**lock the password** 
```
sudo usermod --lock baduser 


--------------------

### Delete bad user account

```
sudo userdel -r baduser 
```
--------------------

### Delete the supplementary group called badgroup.
```
sudo groupdel  -r badgroup 
```
--------------------

### Create a folder called myteam in your home directory and change its permissions to read only for the owner.
```
mkdir myteam
ls -l 
chmod u=r myteam 
cd PERMISSION DENIED
```

--------------------

### Log out and log in by another user

```
su - islam
exit // or ctrl + d 
`----------------
## Using the command Line

* Change the permissions of oldpasswd file to give owner read and write permissions
and for group write and execute  and execute only for the others (using chmod in 2 different ways)
```
sudo chmod u=rw,g=wx,o=x oldpasswd 
or 
sudo chmod 631 myteam
```
 
### What is the maximum permission a file can have, by default when it is just created? 
   
   **2 permissions** 
  
### And what is that for directory  ? 
   
   **3 permissions** 
  
### Change your default permissions to be no permission to everyone then create a directory and a file to verify.

```
umask 0777
mkdir tempdic
touch tempfile
ls -l 
```

  
### What are the minimum permission needed for:

* Copy a directory (permission for source directory and permissions for target parent directory)

  source : rx
  Destination  : wx 

* Copy a file (permission for source file and and permission for target parent directory)

  source : r
  parent : w

* Delete a file : x 
* Change to a directory  : x
* List a directory content (ls command) : x
* View a filecontent (more/cat command) : r
* modify a file content : w


------------

### Create a file with permission 444. Try to edit in it and to remove it? Note what happened.
 $nano file 
 editing and saving using nano gives Denied permission 
  
---------------
### the difference between the “x” permission for a file and for a directory?

* Execute permission on files means the right to execute them, if they are programs . 

* For directories, execute permission allows you to enter the directory (i.e., cd into it), and to access any of its files.

--------------------------
###  Issue the command "sleep 100" in background.

 ```sleep 100&```

--------------------------
### Kill the sleep command.

``` kill sleepId ```

--------------------------
###  Display your processes only
 $ ps    or $pstree

--------------------------
###  Display all processes except yours ( root ) 

```
$ps -U root -u root u --deselect

      --deselect negates  the selection 

--------------------------


### Use the pgrep command to list your processes only

``` pgrep -u root,daemon --list-full ```
