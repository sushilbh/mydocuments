#### How to Push artifacts from Jenkins to Sonatype Nexus

* First, you have to configure the Nexus Jenkins Plugin. For that got to the 
* https://support.sonatype.com/hc/en-us/articles/227256688_How-do-I-configure-the-Nexus-Jenkins-Plugin
* Before you get started, you must first download and install the Nexus Jenkins Plugin from Sonatype Downloads. Then from the Jenkins dashboard, navigate to Manage Jenkins -> manage plugins, proceed to the Advanced tab, and upload the downloaded HPI using the Upload Plugin.
* Now re-start jenkins
*  Configure System
Once you have the plugin installed, the next thing you need to do is configure a Nexus Repository Manager to be able to upload your build artifacts. Once again click on the Manage Jenkins link from the dashboard and then the Configure System link. Under the Sonatype Nexus heading select Nexus Repository Manager 2.x Server from the Add Nexus Repository Manager Server dropdown.
* Now choose >> add Nexus Repository Manager servers
* Server URL will be the  >>when you run nexus dashboard copy < first word:port/nexus>  and give to the below box.
* Credential should be added. For that >add>choose  username with password>> username and password will be the same you have given to the nexus repo>
￼
* ￼￼The Nexus Jenkins Plugin uses Jenkins credentials provider to manage server credentials. To authenticate the connection, use the Add dropdown to create a credentials entry and then select it from the Credentials dropdown. After entering the information for your Nexus Repository Manager, and click the Test Connection button to ensure connectivity to your Nexus Repository Manager installation.  
* Tool Configuration
* For the following example you'll use Maven to build in your project. In order to do so, you need to ensure that you have a Maven installation configured in Jenkins. To do so, navigate to the Manage Jenkins -> Global Tool Configuration and configure a Maven installation as shown below.
