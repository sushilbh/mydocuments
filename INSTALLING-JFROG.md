Installing Jrog Artifactory inside container
-

* We keep artifacts to Jforg artifactory or Sonatype nexus
* FIRST DO GOOGLE SEARCH FOR jfrog artifactory images OR USE FOLLOWING COMMAND
<https://www.jfrog.com/confluence/display/RTF/Installing+with+Docker>

* To start an Artifactory container, use the corresponding command below according to whether you are running Artifactory Pro or Artifactory OSS: below is for oss
* docker run --name artifactory -d -p 8081:8081 docker.bintray.io/jfrog/artifactory-oss:latest

There are 3 types of repo
-
1. local repository >> where your artifactory is stored, when you push docker images it will come to local
2. remote repository >> it will have excess of internet
3. virtual repository >> 


* When you pull image it will search in local repo, if not found it will search in remote repo and save in local repo. And it will also secure jar file.


* Snapshot >>> can be overwritten i,e, If not unique also file
* Release >> it is for production>> should be unique

* Ulimit -n >>> to see the file catpacity
* ulimit
