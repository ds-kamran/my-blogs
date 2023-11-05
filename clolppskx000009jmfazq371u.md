---
title: "Day 05/90 : 1) Linux User Management"
datePublished: Sun Nov 05 2023 16:53:25 GMT+0000 (Coordinated Universal Time)
cuid: clolppskx000009jmfazq371u
slug: day-0590-1-linux-user-management
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1699203031457/3ad0924e-30b8-478a-9780-375af995b42e.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1699203136418/5949e241-be25-4402-ac8f-1502df88a5bc.png
tags: linux, devops, linux-for-beginners, devops-articles, 90daysofdevops-chanllenge

---

User management in Linux is a fundamental responsibility for system administrators. Managing users and their permissions is essential for maintaining system security and providing users with appropriate access to system resources. Here are the key aspects of user management in Linux:

 **User Accounts:**

 **Adding Users:** Use the useradd command to create a new user account. For example: sudo useradd newuser.

Specifying User Details: You can set a user's details using the useradd options, like -c for comments, -s for the login shell, and -m to create the user's home directory.

User Passwords:

**Setting Passwords:** Set a password for a user with the passwd command. For example: sudo passwd username.

Password Policies: You can enforce password policies by configuring the /etc/security/pwquality.conf file and using the pam\_[pwquality.so](http://pwquality.so/) module in PAM configuration.

User Groups:

**Creating Groups:** Use the groupadd command to create a new group. For example: sudo groupadd mygroup.

Adding Users to Groups: Add a user to a group with the usermod command. For example: sudo usermod -aG mygroup username.

User Permissions:

**File Permissions:** Use the chmod command to modify file and directory permissions. For example: chmod 755 myfile.

File Ownership: Use the chown and chgrp commands to change file ownership and group ownership. For example: chown username:groupname myfile.

User Deactivation and Deletion:

**Locking Accounts:** Lock a user account to prevent login using the passwd -l command.

Disabling Accounts: Disable an account by setting an expiration date with the usermod command. For example: sudo usermod -e 1 username (locks the account immediately).

**Deleting Users:** Use the userdel command to delete a user and their home directory if needed. For example: sudo userdel -r username.

Access Control:

**PAM (Pluggable Authentication Module):** Configure PAM to control user authentication, session management, and password policies. The configuration files are typically found in /etc/security.

sudo: Use the /etc/sudoers file to grant or restrict administrative privileges to users.

User Home Directories:

**Home Directory Creation:** The -m option with useradd automatically creates a home directory for the user.

Home Directory Permissions: Ensure that user home directories have appropriate permissions (e.g., 700) for security.

User Account Management Tools:

**useradd, usermod, userdel:** These are command-line tools for managing user accounts.

**passwd:** Used to change user passwords.

**groupadd, groupmod, groupdel:** Manage user groups.

**chage:** Configure user password expiration policies.

**\*\*useradd and usermod with -e option**: Specify account expiration dates.

Monitoring and Auditing:

Regularly monitor user accounts and access logs for suspicious activities.

Implement auditing tools and configure auditd to track user actions.

Backup and Recovery:

Regularly back up user account data and configurations to ensure data recovery in case of accidental deletions or system failures.

User management is a critical responsibility for system administrators. Properly managing user accounts and their permissions is essential for maintaining system security and ensuring that users have the access they need to perform their tasks while adhering to security policies.

Let us begin with some hands-on in User management.

1)    Create 2 users for Dev and Testing team as dev and test respectively.

Check the list of users using command : **ubuntu@ip**:**~**$ cat /etc/passwd

**ubuntu@DevOps**:**~/day2**$ cat /etc/passwd | tail -10

landscape:x:111:116::/var/lib/landscape:/usr/sbin/nologin

fwupd-refresh:x:112:117:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin

ec2-instance-connect:x:113:65534::/nonexistent:/usr/sbin/nologin

\_chrony:x:114:121:Chrony daemon,,,:/var/lib/chrony:/usr/sbin/nologin

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

devops:x:1001:1001::/home/devops:/bin/sh

kamran:x:1002:1002::/home/kamran:/bin/sh

 Create user dev and test:

            **ubuntu@ip**:**~**$ sudo useradd -m dev

**ubuntu@ip**:**~**$ sudo useradd -m test

 check list of users using cat /etc/passwd:

**ubuntu@DevOps**:**~/day2**$ cat /etc/passwd | tail -10

landscape:x:111:116::/var/lib/landscape:/usr/sbin/nologin

fwupd-refresh:x:112:117:fwupd-refresh user,,,:/run/systemd:/usr/sbin/nologin

ec2-instance-connect:x:113:65534::/nonexistent:/usr/sbin/nologin

\_chrony:x:114:121:Chrony daemon,,,:/var/lib/chrony:/usr/sbin/nologin

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

devops:x:1001:1001::/home/devops:/bin/sh

kamran:x:1002:1002::/home/kamran:/bin/sh

dev:x:1003:1003::/home/dev:/bin/sh

test:x:1004:1004::/home/test:/bin/sh

Set password for these users.

2)    Create 2 separate group Dev and Test.

**ubuntu@DevOps**:**~/day2**$ sudo passwd dev

New password:

Retype new password:

passwd: password updated successfully

**ubuntu@DevOps**:**~/day2**$ sudo passwd test

New password:

Retype new password:

passwd: password updated successfully

**ubuntu@DevOps**:**~/day2**$

          Check if the name of the group already exist :  cat /etc/group

         **ubuntu@DevOps**:**~/day2**$ cat /etc/group | tail -10

\_chrony:x:121:

ubuntu:x:1000:

devops:x:1001:

kamran:x:1002:

**ubuntu@DevOps**:**~/day2**$

Note: A group is created by default with the user by same name.

Let us create another group with name developer and tester

            **ubuntu@DevOps**:**~/day2**$ sudo groupadd developer

     **ubuntu@DevOps**:**~/day2**$ sudo groupadd tester

3)    Add both user in both groups.

**ubuntu@DevOps**:**~/day2**$ sudo gpasswd -a dev developer

Adding user dev to group developer

**ubuntu@DevOps**:**~/day2**$ sudo gpasswd -a test tester

Adding user test to group tester

**ubuntu@DevOps**:**~/day2**$

4)    Check the user list of the group:

5)  **ubuntu@DevOps**:**~/day2**$ cat /etc/group | tail -10

6)  ubuntu:x:1000:

7)  devops:x:1001:

8)  kamran:x:1002:

9)  dev:x:1003:

10)     test:x:1004:

**11)     developer:x:1005:dev**

**12)     tester:x:1006:test**

13)     grp1:x:1009:dev

14)     grp2:x:1010:

15)     grp3:x:1011:

16) **ubuntu@DevOps**:**~/day2**$

17) Delete user

**ubuntu@DevOps**:**~/day2**$ cat /etc/passwd | tail -6

devops:x:1001:1001::/home/devops:/bin/sh

kamran:x:1002:1002::/home/kamran:/bin/sh

dev:x:1003:1003::/home/dev:/bin/sh

test:x:1004:1004::/home/test:/bin/sh

newuser1:x:1005:1007::/home/newuser1:/bin/sh

newuser2:x:1006:1008::/home/newuser2:/bin/sh

**ubuntu@DevOps**:**~/day2**$ sudo userdel newuser1

**ubuntu@DevOps**:**~/day2**$ sudo userdel newuser2

**ubuntu@DevOps**:**~/day2**$ cat /etc/passwd | tail -6

ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

lxd:x:999:100::/var/snap/lxd/common/lxd:/bin/false

devops:x:1001:1001::/home/devops:/bin/sh

kamran:x:1002:1002::/home/kamran:/bin/sh

dev:x:1003:1003::/home/dev:/bin/sh

test:x:1004:1004::/home/test:/bin/sh

**ubuntu@DevOps**:**~/day2**$

User Permission:

1)    Change ownership of a file: Change user and group of file and directory.

Chown, chgrp

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu    0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu    0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text1.txt

drwx------ 2 ubuntu grp1   4096 Nov  4 21:01 **majedaar**

**ubuntu@DevOps**:**~/day2**$ chown dev:developer text1.txt

chown: changing ownership of 'text1.txt': Operation not permitted

**ubuntu@DevOps**:**~/day2**$ sudo chown dev:developer text1.txt

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu       0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu       0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 dev    developer    0 Nov  4 20:59 text1.txt

drwx------ 2 ubuntu grp1      4096 Nov  4 21:01 **majedaar**

**ubuntu@DevOps**:**~/day2**$ sudo chown test:tester majedaar

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu       0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu       0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 dev    developer    0 Nov  4 20:59 text1.txt

drwx------ 2 test   tester    4096 Nov  4 21:01 **majedaar**

**ubuntu@DevOps**:**~/day2**$

2)    Change only user of the file not group:

**ubuntu@DevOps**:**~/day2**$ sudo chown test:ubuntu text2.txt

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu       0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu       0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 test   ubuntu       0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 dev    developer    0 Nov  4 20:59 text1.txt

drwx------ 2 test   tester    4096 Nov  4 21:01 **majedaar**

3)    Change group of the directory : majedar

**ubuntu@DevOps**:**~/day2**$ sudo chown test:developer majedaar/

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu       0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu       0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 test   ubuntu       0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 dev    developer    0 Nov  4 20:59 text1.txt

drwx------ 2 test   developer 4096 Nov  4 21:01 **majedaar**

**File permission:**

There are only three types of files in linux: Directory , files, executables

**Octal Notation**

Read, Write and Execute can also be denoted using Octal.

Read (r) – 4, Write (w) – 2, Execute (1) – 1

Consider a file has read, write and execute permissions, then you can denote that in a number as 7 (ie, 4+2+1=7). You will understand about this more in the following sections.

**User, Group and Others (UGO)**

User – The owner of the file. Mostly, one who created the file.

Group – The group which the file belongs to.

Others – Everyone other than the user and the group.

Example :

**ubuntu@DevOps**:**~/day2**$ ls -ltr

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text9.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text8.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text7.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text6.txt

\-rw-rw-r-- 1 ubuntu ubuntu       0 Nov  4 20:59 text5.txt

The permission is divided as : -owner-group-user : -rw-rw-r

1)    Change permission of file text9.txt give owner executable access:

**ubuntu@DevOps**:**~/day2**$ chmod 100 text9.txt

**ubuntu@DevOps**:**~/day2**$ ls -ltr| head -6

total 4

\---x------ 1 ubuntu ubuntu    0 Nov  4 20:59 text9.txt

\-------r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text7.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text6.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text5.txt

2)    Change permission of file text8.txt provide only read access to the user and no access to other.

**ubuntu@DevOps**:**~/day2**$ chmod 004 text8.txt

**ubuntu@DevOps**:**~/day2**$ ls -ltr| head -6

total 4

\-rwxr-xr-- 1 ubuntu ubuntu    0 Nov  4 20:59 text9.txt

\-------r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text8.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text7.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text6.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text5.txt

3)    Change permission of file text7.txt and provide read-write access to group, no access to owner and read access to user.

**ubuntu@DevOps**:**~/day2**$ chmod 064 text7.txt

**ubuntu@DevOps**:**~/day2**$ ls -ltr| head -6

total 4

\-rwxr-xr-- 1 ubuntu ubuntu    0 Nov  4 20:59 text9.txt

\-------r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text7.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text6.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text5.txt

4)    Change permission of a directory recursively:

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu    0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu    0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text1.txt

drwxrwxr-x 2 ubuntu grp1   4096 Nov  4 21:01 **majedaar**

**ubuntu@DevOps**:**~/day2**$ chmod -R 700 majedaar/

**ubuntu@DevOps**:**~/day2**$ ls -ltr

total 4

\---x------ 1 ubuntu ubuntu    0 Nov  4 20:59 **text9.txt**

\-------r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text8.txt

\----rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text7.txt

\-rwxrwxr-x 1 ubuntu ubuntu    0 Nov  4 20:59 **text6.txt**

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text5.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text4.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text3.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text2.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text10.txt

\-rw-rw-r-- 1 ubuntu ubuntu    0 Nov  4 20:59 text1.txt

drwx------ 2 ubuntu grp1   4096 Nov  4 21:01 **majedaar**

**Additional information :**

 How to change hostname in ubuntu:

 Check hostname : *cat /etc/hostname* or type *hostname*

 To change the hostname

 *hostnamectl set-hostname &lt;new\_name&gt;*