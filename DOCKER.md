#### Installation of Docker in ubuntu
* step 1: curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
* step2: sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
* step 3: sudo apt-get update
* step4: sudo apt-get install -y docker-ce
* check docker version
   docker --version
   
   
 **installation of docker-compose**
* tool for defining and running multi container docker applications
* use yaml files to configure application services. (docker-compose.yml)
* can start all services with a single comand: docker-compose up
* can sstop all sevices with a single command: docker-compose down
* can scale up selected services when required.

* step1: install docker compose>>> once you have installled in your machine docker compose install automatially in           mac and   window. for that
* go to terminal and run >> docker-compose -v ->it will show your docker compse version OR docer-compose version

**FOR LINUX**
* sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
* sudo chmod +x /usr/local/bin/docker-compose
* docker-compose --version
* mkdir my_appcd my_app
* cd my_app
* nano docker-compose.yml



######OR FOLLOW FOLLOWING LINK#####
https://linuxize.com/post/how-to-install-and-use-docker-compose-on-ubuntu-18-04/
....

DOCKER

**Purging All Unused or Dangling Images, Containers, Volumes, and Networks

* IMPORTANT NOTE: to change the content of file inside container >> apt-get update >> apt-get install vim >> change the content

* sudo systemctl restart docker >>> to restart docker
* service docker start >> to start docker
* service docker stop >> to stop docker
* sudo user mod -a -G docker ec2-user  (where, docker is group and ec2-user is user) 
* docker inspect container id >>>> to see all the details of container 
* docker system prune >>will clean up any resources — images, containers, volumes, and networks — that are dangling (not associated with a container):
* docker system prune -a >> remove any stopped containers and all unused images (not just dangling images)
* docker rmi ImageID >> remove image
* docker images -f dangling=true >> list the dangling images
* docker images purge >> remove dangling images
* docker images -a |  grep "pattern" >> list images according to a pattern
* docker images -a | grep "pattern" | awk '{print $3}' | xargs docker rmi >> remove images according to a pattern
* docker rmi $(docker images -a -q) >> removing all images
* docker ps -a >> show the list of all container
* docker rm ID_or_Name ID_or_Name >> removing a container
* docker 
* docker ps -a -f status=exited >> list all exited container
* docker rm $(docker ps -a -f status=exited -q) >> remove all exited container
* docker rm -f container id >>> to remove running container
* docker volume ls >> list the docker volume
* docker volume rm volume_name >> remove the volume
* docker volume prune >> removing dangling volume

Dockerfile:
-
1. Make one dir.  >> mkdir Dockerfile >>> vim Dockerfile
2.  FROM ubuntu
	MAINTAINER ram <ram@gmail.com>
         RUN apt-get update
         CMD [“echo”, “Hello world”] >> save & exit
3. docker build .  >>> if you are in place of Dockerfile otherwise you can give a path
4.  docker build -t myimage1 .  Where my image1 is tag name
5.  docker run image1 or image id >>> to run docker container

Docker Compose: (it is use for running multi container)
-
1. docker-compose version >> show the version
2.  Create docker compose file default is docker-compose.yml
3.   mkdir docker-compose.yml >> vim docker-compose.yml   
        Version: ‘3’
        Service:
            Web:
                  image: nginx
                  port:    
 		 - 9090:80
             database:
		image: redis
4. Check the validity of the file by command >>> docker-compose config
5. Run docker-compose .yml file by command >>> docker-compose up -d  where -d is detach mode
6. docker-compose ps
7. Docker-compose down >> to stop container       
Run docker-compose config

How to scale services:
-
docker-compose up -d --scale database=4 >> it will create 4 database images. If you do docker ps you will see 4 container running.

Docker volume:
-
Decoupling container from storage
Share volume (storage/data) among different containers
Attach volume to containers
On deleting container volume does not delete.

1. docker volume —helpd
2. docker volume create myvolume  (where, myvolume is volume name) 
3. docker volume ls >> list the volume
4. docker volume inspect myvolume >>> show the details
5. Docker volume rm myvolume >>> to remove volume

Use of Docker volume to create container:
-

* docker container create --name jenkinsrun -it --mount source=myvol1,target=/demo-test jenkins

* docker pull jenkins >> comes from docker hub
* docker run -p 8080:8080 -p 50000:50000 jenkins (where, first 8080 is host port, second 8080 is container port and 50000:50000 is API)
* docker run --detach --name myjenkins -v myvolume:/var/jenkis_home -p 8080:8080 -p 50000:50000 jenkins 
(Where, myvolume get data from /var/jenkins_home)
* When you run this command jenkins will run where >> create jobs>>testjob>>freestyle>> execute command >>’ls’  >>apply and save
* Now if you run this command again with different name in different port but can use same volume ie,
Docker run -name myjenkins1 -v myvolume:/var/jenkins_home -p 9090:8080 -p 60000:50000 jenkins >> it will also run and it will have same job inside jenkins. 

Docker swarm
-

