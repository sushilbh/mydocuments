#### <chef commands>

1. command to install clint software --->curl -L https://www.opscode.com/chef/install.sh | bash
2. vi dir.rb
	directory '/tmp/mydir' do
	  owner 'root'
	  group 'root'
	  mode '0755'
          action :create
        end
3. chef-apply dir.rb
4. more dir.rb ---> is like cat in linux
5. In above file if we don't mention action create it will create automatically because every resource defult action is create.
6. If you run chef-apply dir.rb again it will say action create and upto date.
7. vi dir.rb
        directory '/tmp/mydir' do
	  owner 'root'
	  group 'root'
	  mode '0755'
          action :create
        end
	
	 file '/tmp/mydir/index.php' do
	  content '<html>This is a place holder for the home page.</html>'
	  owner 'root'
	  group 'root'
	  mode '0755'
          action :
        end
8. chef-apply dir.rb ---> it will create index.php file inside mydir

## Creation of Hosted Chef-server
-

* In hosted chef-server we will create orgination
* For that goto <manage.chef.io> 
* sign in
* goto orgination and create orgination <testdevops>
* download the starter kit (BUT MAKE SURE DO NOT DOWNLOAD STARTER KIT IN PRODUCKTION BECAUSE IT WILL RE-SET   YOUR AUTHENTICATION KEYS).
* Unzip the starter kit file>>when you unzip you will find chef-repo. if you go inside chef-repo you will   contain .chef server which have knife.rb and   .pem   file. knife.rb will maintain your server details and   authentication details.
* If you want to work with the chef-server, you have to be in a directory called chef-repo. If you are in a   directory called chef-repo, you can able to     stablish a connection between work station to the chef with   the help of the knife.rb.

## Prepare workstation
-
1. we need chef-repo folder (it will contains the authentication details) (it will come when you download the starter kit)
2. we need chefdk (chef development kit) (it will contains not only clint software but lot of software that includes testing your cookbooks or your          invironments kind of a things)
3. Goto <downloads.chef.io> select chef development kit>> you will find different o/s.
4. if you are working on linux machine copy the link address you need and <wget pest that link>
5. you may need to download the rpm commnad will be <rpm -ivh chefdk........>
6. to verify all package are porperly installed or not commnd will be <chef -verify>
7. If you want to make linux server as work station upload the chef-repo from your local machine to the linux server you can use scp command or you can use     Winscp for window.

## creating Cookbook
-
1. chef generate cookbook <cookbook name>

2. cd <cookbook-name>
3. knife cookbook upload <cookbook name> (it will give version if you check more metadata.rb you will see    it)
4. once you upload the cookbook into chef-server. you will configure that cookbook into different vms. for that execute below commands.
* knife bootstrap <ip of vm> -X username(ec2-user) -p passwd(password of the user) --sudo -N appserver
5. 
