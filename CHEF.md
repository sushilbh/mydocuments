#### installlation of chef server
* goto url <manage.chef.io>
	* create an account
* if you delete starter kit >>>once you go inside your account >>> goto orginazation>> manage orgn>>choose orgn name>>you will see starter kit
* download chef-starter and push it into github repo
	 
(goto download-> git clone repo-> copy the chef folder into that repo-> git add, commit and push)


1. chef server
...............
manage.chef.io
	create an account
download chef-starter and push it into github repo

2. workstation (local machine)
...............
download chefdk
goto cmd
	git clone gitrepo-url(chef-starter)

3. chef-client (nodes)
...............

4. connecting workstation with chef-server to nodes
.........................
knife ssl fetch
knife ssl check

bootstrap for windows machine
..............................
knife bootstrap windows winrm [client-ip/hostname] -N [node-name/hostname/anyname] -x [username/login name] -P [password]

bootstrap for linux machine
.............................
knife bootstrap <node-IP> -N <node-name> --ssh-user ec2-user --sudo --identity-file ~/Downloads/ramhari.pem -y


aeHe&*pEQMrP(nJ(XsoRit8sX(X2&ajh

Administrator

knife bootstrap windows winrm "3.95.162.147" -N "windows" -x "Administrator" -P "aeHe&*pEQMrP(nJ(XsoRit8sX(X2&ajh"

5. ping ip
	client-server/remote desktop-> firewall-> advanced-> public off

6. knife node list
knife node show <node-name> ->
knife node edit <node-name>
export "EDITOR=nano" (it will allow you to edit the file)

goto /cookbooks folder (to create a new cookbook)
chef generate cookbook <cookbook-name>
cd <cookbook-name>

............................................................

commands
...........
knife cookbook upload <file-name: eg-test>
more metadata.rb
vi metadata.rb
ls
mv dir.rb chef-repo/cookbooks/test/recipies/default.rb
