#### GIT-GITHUB

* git init	>>> Create a new local repository with the specified name  .git
* git clone <existing central repo link>	>>> Download the project and its entire version of History.
* git remote add origin <remote repo link>	>>> Adding local repo to central repo in remote server.
* git pull origin master	>>> If anything change direct in central repo in remote server will pull in local repo.
* git status	>>> To see the file between working directory and index.
* git add abc.txt	  >>> Adding abc.txt file in index and ready to commit
* git -A OR  git add . 	>>> Adding all files together 
* git commit -m “commit”	>>> Committing one file
* git commit -a -m “commit”	>>> Committing multiple files together
* git branch Firstbranch	>>> Creating branch as Firstbranch                              OR
* git checkout -b Firstbranch	>>> Creating branch as Firstbranch and switch into firstbranch
* git checkout Firstbranch	>>> Switch into firstbranch
* git branch -d Firstbranch   >>>> to delete Firstbranch 
* git merge Firstbranch	   >>> All branches need to be merged to the master. Master branch is the destination, staty in master and merge firstbranch
* git push origin firstbranch	  >>> Stay in firstbrach if you want to push file in firstbranch in remote server.
* git push origin master	>>> Staty in master if yu want to push file in master branch in remote server.

REVERT CASE
------------

Make abc.txt file. Write hello as content and commit. Now make change in that file write hello there and commit it again. Now you want previous version with  hello only. Command is ‘git log’ where you find abc.txt file. Copy the first 8 digit of 40 degit hexadecimal code. Then, git checkout pest that 8 digit code filename. Now if you cat abc.txt you will see only hello.
OR  git log --oneline > it will show first line. Then git revert paste seven digit of code. Now : you cat abc.txt you will see hello only. Now if you want to go back again >> git revert HEAD > it will show hello there again.

NOTE: to go the previous commit>> git reset commit id --hard

* git log	   >>> It will show the commit, author and date.
* git log --before=”date” 	>>> Will give date log
* git log –author=”author name” 	>>> It will show the commit made by author

STASH
-------

Stash takes the current state of the working directory & index and puts in stack for later and gives you back a clean working directory. If you are middle of something and want to jump to another task and don’t want to lose your current edits.
When you add files into index but before commit and you need a clean working directory

* git stash -u	 >>> Now check git status working directory will be clean
* git stash list 	>>>> It will show the list of stash
* git stash show 	>>> You can inspect stash files here
* git stash apply	>>> You will get old record
* git stash drop	>>> When you done with the stashed item or want to remove from list run git stash drop command.

MERGE CONFLIT
--------------
* git pull --rebase origin master 	
* git status	>>> To see where the conflict is
* git mergetool enter enter 	>>> enter enter 2 times and make change save and exit > 2 or 3 times
* git rebase --continue	
* git push origin masters	

Note: deleting remote branch in github from cli/terminal
-------------------------------------------------------
* git push origin --delete branchname
