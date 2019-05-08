JENKINS INSTALLATION
-

step 1: Installation of OpenJDK
-
1. Install the OpenJDK 8:
2. sudo yum install java-1.8.0-openjdk
3. If you have more than one Java version installed on your system use the following command to switch versions:
4. sudo alternatives --config java
5. Make sure your system is using the correct JDK:
6. java -version 

step2: Installation of Jenkins
-
* sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
* sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
* sudo yum install -y jenkins

To check the STATUS of Jenkins:
-
* systemctl status jenkins
* systemctl restart jenkins
* sudo service jenkins start/stop/restart

Jenkins Home
-
* .jenkins will be at /var/lib/jenkins
* Workspace will be at  /var/lib/jenkins/workspace

* /etc/sysconfig/jenkins >>> if you want to change the port 
* /var/lib/jenkins/secrets/initialAdminPassword

Maven Installation (In order to run maven java should be installed)
-
* go to below rul
* http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
* sudo tar -zxf apache-maven-3.6.0-bin.tar.gz
* Add path >>> first go inside /opt/apache-maven-3.6.0/bin
* PATH=$PATH:/opt/apache-maven-3.6.0/bin
* echo $PATH >>> to check whole path

Add path for only one user like ec2-user
-
go inside .bashrc and add following path
export PATH=$PATH:/opt/apache-maven-3.6.0/bin

NOW, after you add path exit in terminal and reconnect machine again.

OR add path for all user
-
* Go to >> /etc/profile.d/     
* create something called env.sh and add following path.
* export PATH=$PATH:/opt/apache-maven-3.6.0/bin

NOTE: .bashrc is for local user and profile.d is for all users
-


JENKINS

* If you forget password Jenkins Home >>> /var/lib/jenkins>>config.xml>>> go inside and find security>> use security is true make it false and restart jenkins.

NOTES
-
Once you build the job and execute package stage it will create .jar file inside workspace/pipeline/target 
Now,  another step will be send to artifacts, and create surfer reports.
For artifacts>>> goto pipeline syntax>> select artifacts> File to archive will be >>> target/**/*


After package state you will perform following steps
-
1. Archive >>>target/surefire-reports/* or target/surefire-reports/*.xml OR **/target/*
2. Junit test >>> target/surefire-reports/*.xml OR **/target/surefire-reports/*.xml
3. Generate surefire reports(you can add in test step also or can create new stage) this will create site dir inside target dir 
4. Now publish that surefire report in html. For that install html publish plugin in (pipeline manage plugin) then HTML directory to archive
5. HTML directory to archive>>>target/site/
6. Index page[s]>>>surefire-report.html





