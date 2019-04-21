#### TOMCAT INSTALLATION

Prerequesite >>>jdk
---------------------

INSTALLATION OF TOMCAT 
1. go to url> search for tomcat 8 download> copy link address of tomcat tar.gz file>  wget <link> untar the file> 
sudo tar -zxvf apche tomcat ….> go inside apche>  bin> there is startup.sh and shutdown.sh file
Check if tomcat is started or not
ps -ef | grep tomcat
Give change the privilege >> chmod +x startup.sh
                   				  chmod +x shutdown.sh
To start tomcat go inside  bin and execute the command >> ./startup.sh 
 To shutdown tomcat go inside bin and execute the command >> ./shutdown.sh 
Now to start from outside add the path of the Tomcat
ln -s /opt/apache-tomcat-8.5.31/bin/startup.sh  /usr/local/bin/tomcatup
Where, ln (lowercase L) -s is command
                /opt/apache-tomcat-8.5.31/bin/startup.sh >> tomcat path
              /usr/local/bin/ >>> adding path here 
             tomcatup >> givenname to start tomcat
For, shutdown,  ln -s /opt/apache-tomcat-8.5.31/bin/shutdown.sh  /usr/local/bin/tomcatdown
 Apache tomcat run default port in 8080 but jenkins also run in 8080 so to change the tomcat port>>>
Go inside >> opt/apache-tomcat-8.5.31/conf/server.xml
vi that server.xml >> connecter port change to 8090 >>connecter executer to 8090 and restart the service for that>> tomcatdown>>> it will stop the tomcat
             tomcat>> it will start the tomcat
To inter manager app
find / -name context.xml >> it will give the list of the locations where you can find context.xml file in two difference locations
 Once you go inside context.xml in both locations  execute following command in the line start with <Value….
IN the beginning <!-- <Value
IN the end of same line /> --> now restart the tomcat and try to access the manager app it will prompt sign in box  
NOW,
To create user with roles >goto terminnal(server)> opt/apache-tomcat-8.5.31/conf/tomcat.users.xml>>
vi that tomcat.users.xml>> goto end of the page>> in-between tomcat users>>
