# LINUX COMMANDS - ALTSCHOOL ASSIGNMENT 1

INTRODUCTION

 Proper user account management enables Linux to enforce access controls (permissions) and audit who does what on the system. User and group management are two must-have skills for every Linux administrator. Knowing the skills and commands in user admin and group admin helps ensure one is ready for the day-to-day user and group administration tasks a sysadmin is called on to do.

1.  HOW TO CREATE A USER ON LINUX:

In oder to create a user on Linux, the following commands must be followed
First you need run Vagrant up to configures guest machines according to your Vagrantfile and run Vagrant ssh to get access to the shell.

When you get access to the shell you run the Command "sudo useradd USERNAME in my case the USERNAME created was Mercy. The sudo command allows you to run programs as another user, by default the root user.
You need to create a password for the user so you run the command "sudo passwd Username". You will be promtpted to enter and confirm the password. when you recive the feedback "password updated successfully created" then you know you have successfully created a new user with password.

![Alt text](<New folder (2)/CREATING A USER ON LINUX.png>)


2. CREATE A USER WITH EXPIRY DATE:

To create a user with expiry date , run the command "$ sudo useradd -e YYYY-MM-DD username". Assuming we want the password to expiry within a week, you run "sudo useradd -r 2023-08-31 Mercy" where Mercy is the User i created. Create a password again using " sudo passwd Username" and reconfirm the password.

In order to check user password expiration run the command "sudo chage -l Test,where Test refers to the name mercy". This will give you number of days of waring before password expire.

![Alt text](<New folder (2)/CREATING A USER WITH EXPIRY DATE.png>)


3. HOW TO PROMPT A USER TO CHANGE PASSWORD LOGIN:

To prompt a user to change password login, run the command "sudo passwd -S username where username is Mercy", then run " sudo passwd e- user to expire a user’s password and force them to change it at the next login.

Again run the command "su Mercy' To make the the user change their password at the next login. But before setting a new password, they'll have to provide the current password.

In Linux, the chage command sets up an expiration policy for user passwords. You can use it to expire the user password immediately or after a certain number of days. 
To check the password's current aging information, run the command "sudo chage -l username".

![Alt text](<New folder (2)/HOW TO PROMPT A USER TO CHANGE PASSWORD LOGIN.png>)


4. HOW TO ADD A USER TO A GROUP:

Adding a user to a group in Linux is a common task that system administrators perform. It allows users to access resources that are only available to members of that group.

In order to add a user use the command " sudo groupadd groupname".

To display complete user information, including all the groups of which a user is a member of, use the id command followed by the username "id username"

![Alt text](<New folder (2)/ADD A USER TO A GROUP.png>)

 You also run sudo Visudo to test if the group has been added

![Alt text](<New folder (2)/SUDU VISUDO.png>)


5. HOW TO CREATE A USER WITHOUT HOME DIRECTORY

To create users without their home directories, '-M' is used. So you will run the command "useradd -m Esther" and this wil turn off the creation of the user's home directory
![Alt text](<New folder (2)/HOW TO CREATE A USER WITHOUT HOME DIRECTORY.png>)