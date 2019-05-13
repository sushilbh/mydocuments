IMPORTANT REFERENCE
-
Deploy .jar or .war file to another server or S3 bucket
-
##  FIRST: deploy to another server
* To deploy artifacts to target server >>> choose ssh agent in pipeline syntax >>> add key >>> ssh usernamewith private key >>> Id and Desctiption can be anything >>> user should be the user of target server i,e, ec2-user or deployuser
* Then, do Keygen in agent machine or another fresh mac terminal >>>> copy public key to .ssh/authorized_keys in target machine>>> give 600 permission to authorized_keys and 700 to .ssh

* command will be like this >>>> sh "scp -o StrictHostKeyChecking=no target/my-app-1-RELEASE.jar ec2-user@3.82.47.15:/home/ec2-user"

## SECOND: deploy to S3 bucket
* add some plugin in managejenkins>>manage plugings
- amazon ec2 plugin
- amazon S3 bucket credential
- aws global config plugin
* Install aws CLI and config it, use below url to install cli
* https://docs.aws.amazon.com/cli/latest/userguide/install-bundle.html
Now,
* create s3 bucket
* choose withcredential:bind credential... in pipeline syntax >>> bindings >>> add >>> aws access key and secret key >> add key >>> choose aws credentaials >>> give access key and secret key
note: accesskey and secret key get from IAM user create you will see...

* command will be like this: withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-secrect-key', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']])
* sh "aws s3 cp target/my-app-1-RELEASE.jar s3://ghimire-bucket/"

# To setup email
* install mutt in agent machine >>>> sudo yum install -y mutt
* and choose timeout in pipeline syntax

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


* remote_src: true >>> to move file from one destination to another destionation in target machine
## install and edit inside conatiner
* apt-get update
* apt-get install vim


