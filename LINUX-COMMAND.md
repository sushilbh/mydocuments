
#### LINUX COMMANDS
* cd ../../..	 >>> Go back 3 parent directories
* cd -	         >>> Go the previous dir. (where were you into)
* mkdir -p first/second/third >>> Create parent directories
* cd -p first/second/third	>>> Go third dir. at once.
* cp -r  >>> Copy complete dir.
* cp  abc.txt   ~/first/second >>> Copy abc.txt file to second dir. using BACKWARD approach
* cp  ~/first/abc.txt  ~/first/second >>> Copy abc.txt file from first dir. to second dir. using FORWARD approach
* rm *.txt 	>>> Delete all file with .txt extension
* rm * 	 >>>Delete all files
* rm -i	  <file name> >>>>>To prevent yourself from accidentally removing 
* sudo su  >>>	Take you to the root
* ctrl + l (lower case of L)	>>> Clear terminal
* ctrl + a 	>>> To go first word of syntax
* ctrl + e 	>>> To o last word of syntax
* mv mydir myfirstdir	>>> Rename mydir to myfirstdir

** MAKING  USERS AND GROUPS**
* useradd superman	>>> Make superman  as user
* cat /etc/passwd	>>> See the user
* groupadd sperheros 	>>> Make superheros as group           g = primary group , G = secondary group
* cat /etc/group	  >>> To see the group
* useradd -G superheros ironman	>>> Adding ‘new user’ ironman in existing secondary group superheros
* usermod -G superheros superman	 >>> Adding ‘existing user’ superman in secondary group superheros
* gropuadd  avengers	>>> Adding new group avengers
* usermod -G superheros, avengers superman	>>> Superman is added in both group superheros and avengers
* usermod -g avengers superman	>>> It changes the primary group of superman. Now avengers is a primary group
* id superman	>>> It gives the details of superman
* passwd superman 	>>> To create password to the user superman
* sudo userdel superman 	>>> To delete user superman
* sudo  groupdel superheros	>>> To delete group superheros
* df -h 	>>> Check the free machine space
* du -h	>>> Check used machine space
* ps -aux	>>> Give all the running, stop and pause processor 
* kill code no	>>> Where conde no is processor numer
* kill -9 	>>> To force kill the desired processor
* kill -15  	>>> To kill along with child processor
* kill  -19	>>> Pause the processor
* Kill -18 	>>> Resume the processor 
* Ps	>>>>> To see all processor
