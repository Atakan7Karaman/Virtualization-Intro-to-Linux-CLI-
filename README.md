# Virtualization (Intro to Linux CLI)

## Objective

This Virtualization Lab was designed to get us comfortable with the Linux CLI.

### Skills Learned

- How to navigate using the command line interface.
- How to open/read text files.
- How to make new directories and files using the CLI.
- How to create new users and new groups.
- Adding and removing users from groups, and managing permissions.

## Steps

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/fa5e757f-2b49-49d5-ac88-8c4ef73e4fec)

I started this lab off by trying out some commands that allowed us to our present working directory. I navigated to the Documents directory, and finally, the last command that I input, “cat example.txt” allowed me to see the content of the text document that I had navigated to.

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/fbb400e2-787c-4a32-a38b-eae1973cc40d)

With the last couple of steps, I created a new directory named mydir, copied the example.txt and named the new file newfile.txt, and renamed the example.txt to oldfile.txt. I also moved the newfile.txt to the home directory, and the “ls -l newfile.txt” allowed me to see additional information about the text file.

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/79f4a12d-c867-4ce3-ad6c-fd39f006dd89)

With the last couple of steps, I have removed the newfile.txt as well as the oldfile.txt, and I have even removed the mydir directory. The last command, “ip r” allowed me to see information about the system’s network interface configurations. 

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/005c2194-1d5b-4065-8e3c-4055fe095bb8)

In the last couple of steps I tested out the ping command, and also used the “netstat -tpn” command. The second time was with elevated privileges because of the word “sudo”.

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/7ed9c1d7-9b13-4e85-bc06-95cb8f9b5c8d)

This is the command that we have to use in order to create a new user. 

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/32aa7351-9c45-4d70-9f7a-07e00f9700fc)

 The last command allowed us to create a new group called accounting.

 ![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/d33ccafa-9479-47dc-9f18-2ba9d2aa93f3)

 In the last couple of steps, I created a new password for the demo user, and I also added the mgs650student account to the group “Students”. 

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/d362faa4-8e9e-4c1b-aead-71c2b5a4c9fd)

We used some commands to list all of the groups in the system, and then we used a command to remove a user from a group. 

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/4cd61251-ae6e-4fab-b10e-7c7004a89804)

The last couple of steps had to do with managing permissions, specifically, we learned about the chmod and chown commands. 

### Independent Examination

In this part of the assignment we had to use what we learned so far to adjust the groups, the owners, and the permissions for the various groups that were in the virtual machine the lab was hosted on. We were given a description of the desired states that the groups should be in, as well as a general description of the employees in the company and the roles/responsibilities that these employees have. Once we got the groups to their desired state, we used the “ls -l /G/” command to display the final state of the groups. 

![image](https://github.com/Atakan7Karaman/Virtualization-Intro-to-Linux-CLI-/assets/164254350/b47d9ab0-d807-4d8a-824b-ec586382e340)

 The above picture has both “ls -l /G/” and “getent group sudo accounting finance hr it legal” commands. Below I have also listed the steps I took to get to the above results. 

 My workflow for the Independent Examination is as follows: 

1. I created the Accounting directory using “mkdir”, and moved it into the /G/ directory.
2. I created an “accounting” group using “sudo groupadd accounting”.
3. “chgrp” command allowed me to change the owner of the “Accounting” directory to the group “accounting”.
4. I created an admin account for the systems administrator, as I figured it would be best if he had different accounts for when he needed elevated privileges and for everyday use. This new account is named “tim-admin” and I also added him to the “sudo” group using “sudo usermod -a -G tim-admin sudo”.
5. “chown” command allowed me to change the owner of the different directories to the sysadmin account that I created, “tim-admin”.
6. “chmod” allowed me to change the permissions of the different directories. I decided to allow full read write and execute privileges to both the owner of the directory, the sysadmin, as well as the members of the group. The people not belonging to that group can’t alter or read the files in the directory.
7. Now that the directories had the right groups, owners, and permissions, I moved on to making sure all of the users were in the right groups.
8. I used the “usermod -a -G” command to add users to groups, and the “gpasswd -d” command to remove users from groups. In this step, I also made the decision to remove the CEO (mark) from the various directories. I figured if one of these groups wanted the CEO to know something, they could probably generate a report and give the CEO the information that way. I didn’t see a reason for letting Mark have editing privileges over every group in the company. The final change I made here was that since I created an admin account for the sysadmin, I removed the regular account that “tim” has from the “sudo” group, and just kept it in the regular “it” group.


