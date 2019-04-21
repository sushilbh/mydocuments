JENKINS INSTALLATION
-

Installation of OpenJDK
-
1. Install the OpenJDK 8:
2. sudo yum install java-1.8.0-openjdk
3. If you have more than one Java version installed on your system use the following command to switch versions:
4. sudo alternatives --config java
5. Make sure your system is using the correct JDK:
6. java -version 
Installation of Jenkins
* sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
* sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
* sudo yum install -y jenkins

To check the STATUS of Jenkins:
Systemctl status jenkins
Systemctl restart jenkins
* sudo service jenkins start/stop/restart

.jenkins will be /var/lib/jenkins
Workspace will be  /var/lib/jenkins/workspace
Jenkins Home
/etc/sysconfig/jenkins >>> if you want to change the port 
/var/lib/jenkins/secrets/initialAdminPassword

Maven Installation (In order to run maven java should be installed)
http://mirror.olnevhost.net/pub/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
sudo tar -zxf apache-maven-3.6.0-bin.tar.gz
Add path
export PATH=$PATH:/opt/apache-maven-3.6.0/bin
============================================================================================================
JENKINS
If you forget password Jenkins Home >>> /var/lib/jenkins>>config.xml>>> go inside and find security>> use security is true make it false and restart jenkins.

Once you build the job and execute package stage it will create .jar file inside workspace/pipeline/target. 
Now,  another step will be send to artifacts, and create surfer reports.
For artifacts>>> goto pipeline syntax>> select artifacts> File to archive will be >>> target/**/*
In advance option select
Use default excludes
Treat include and exclude patterns as case sensitive
 When you do artifact step in test stage before package stage, you will get watch symbol in building. now, Junit test test functionality of program.
Choose junit in pipeline syntax and Test report XMLs>>>>target/surefire-reports/*.xml






After package state you will perform following steps
1. Archive >>>target/surefire-reports/* or target/surefire-reports/*.xml OR **/target/*
2. Junit test >>> target/surefire-reports/*.xml OR **/target/surefire-reports/*.xml
3. Generate surefire reports(you can add in test step also or can create new stage) this will create site dir inside target dir 
4. Now publish that surefire report in html. For that install html publish plugin in (pipeline manage plugin) then HTML directory to archive
HTML directory to archive>>>target/site/
Index page[s]>>>surefire-report.html
5. 





