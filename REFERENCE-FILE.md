IMPORTANT REFERENCE
-
Download files from server to your local machine 
-
* (stay in local machine where your aws key is ie, download or desktop)
* scp -i ramhari.pem -r ec2-user@IP:/home/ec2-user/ansible1 .
* Where,
 ** scp -i >>>command
** ramhari.pem >>key name
** -r >>> for folder no need for file
** ec2-user >>> name of the user
** Ip >>public ip of the machine from where you want to download the files/folder
** : >>>colon
** /home/ec2-user/   >>>>> path of the folder OR file WHERE your ansible1 is located
** ansible1 >>>> is the folder you want to download
** . (dot) >>>> here

Transfer file from local machine to server:
-
* scp -i ramhari.pem ~/Download abc.txt ec2-user@IP:/tmp
** Where,
** scp -i >>>command
** ramhari.pem >>key name
** ~/Download >> path of the file (where is your file you want to transfer)
** abc.txt >> file you want to transfer
** ec2-user >>user
** ip >> public Ip of the machine where you want to upload the file
** : >>colon
** /tmp >>>>you want to move under tmp dir.

Give root level privilege to deployuser
-
* sudo useradd deployuser
* cd /etc/sudoers.d >>>  go inside this file
* vi deployuser >>> create deployuser file 
* deployuser    ALL=(ALL)    NOPASSWD:ALL

Ansible
-
* ansible -I hosts db -a “yum install -y git” -k --sudo
* ansible -I hosts db -a “git --version” -k --sudo

* Sudo useradd deployuser
* Passwd deployuser >>> to create password for deployuser

* ssh-copy-id ec2-user@public ip of target machine >>> to communicate with other machine you don’t have to share public key
** Where,
** ssh-copy-id >>> is command 
** Ec2-user >>> is name of user
** Ip of target machine >>> is target machine public IP


*remote_src: true >>> to move file from one destination to another destionation in target machine
