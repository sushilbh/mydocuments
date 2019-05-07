#### installlation of chef server
...............
manage.chef.io
	create an account
download chef-starter and push it into github repo
(doto download-> git clone repo-> copy the chef folder into that repo-> git add, commit and push)

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
knife bootstrap windows winrm [client-ip/hostname] -N [node-name/hostname/anyname] -x [username/login name] -P [password]
knife bootsrap <ip> --ssh-user ec2-user --sudo --identity-file ~/.ssh/Feb.pem if ec2
knife bootstrap node_domain_or_IP -x username -i samekey -N chef_name_you_want --sudo


aeHe&*pEQMrP(nJ(XsoRit8sX(X2&ajh

Administrator

knife bootstrap windows winrm "3.95.162.147" -N "windows" -x "Administrator" -P "aeHe&*pEQMrP(nJ(XsoRit8sX(X2&ajh"

5. ping ip
	client-server/remote desktop-> firewall-> advanced-> public off

6. knife node list

............................................................

commands
...........
knife cookbook upload <file-name: eg-test>
more metadata.rb
vi metadata.rb
ls
mv dir.rb chef-repo/cookbooks/test/recipies/default.rb

knife search node "platform:centos"
	will list all the centos servers
