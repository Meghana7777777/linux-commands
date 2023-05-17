File Management:
================

* ls - used to list the contents of the folder or directory
  ex : ls 
       desktop  downloads  pictures games file1 file2

* ls -l -used to display the contents of the folder
  ex : ls -l
       drwx-rw-x --------------desktop 
        rw--rw-x --------------file1

* ls -a -used to display hidden files (.)
  ex : ls -a
       desktop download  .log file .file3 pictures file1 file2
 
* ls -al - formatted listing with hidden files
  ex : ls -al
        drwx-rw-x --------------dektop 
         rw--rw-x --------------.file3

* cd - change directory (go to the home directory)

* cd .. - which represents the parent directory
        root@meghana:dic1/dic2$
   ex : cd ..
        root@meghana:dic1$

* cd ../.. - at a time move to two parent directories
  ex : cd ../..
       root@meghana:$

* pwd - used to dispaly current working directory
  ex : pwd
       meghana

Creating Files:
===============

* touch - used to create files or update files
  ex : touch employeefile1
       touch file2 file3 ---- at a time create number of files

* echo > - used to create file and place standard input into the file
  ex : echo "hello world" > file.txt
       "hello world"

* cat > - used to create new file and place standard input into the file
  ex : cat > file.txt
       this is my first project
      ( ctrl+d - used to exit from the cat interface and save the file)

* nano - used to create files 
  ex : nano file name

* vim/vi - used to create files
  ex : vim/vi file name
   --  i - insert mode 
   --  esc - to exit from the insert mode 
   --  wq - to save and exit
   --  q! - forcely exit without saving file


 Creating Directories:
=======================

* mkdir - used to create directory or folder 
  ex : mkdir fol1
       mkdir fol2 fol3 ---at a time create number of directories/folders 
       mkdir fo1l/fol2  ---create a sub folder inside the fol1 
       mkdir -p fo1/fol2 ---at a time create sub folder and parent folder

Removing Files & Directories:
=============================

* rm - used to remove file
  ex : rm filename

* rmdir - used to remove empty directories/folfers
  ex : rmdir fol/direc

* rm -rf - used to remove non empty folders/directories
  ex : rm -rf fol/direc --- rf - recursively forcely

* rm -rf / - used to remove entire files in root 

Coping & Moving Files and Folders:
==================================

* cp - used to copy files and folders from one location to another location
  ex : cp file1 file2 or cp fol1 fol2
                        
* mv - used to move files/ directories from souce to destination 
     - used to rename file/ folder
     - move files / folders from souce to destination it removes previous file / folder
  ex : mv file1 file2 or direc1 direc2

Viewing Contents in a file:
===========================

* cat - used to display the content of a file
  ex : cat filename

* head - used to display the content of a file 
       - by default it displays first 10 lines 
  ex : head filename
  ex : head -n 4 filename --it displays top 4 lines of file
  ex : head -n -4 filename --it removes last 4 lines display remaining lines in a file

* tail - used to dispaly the content of a file 
       - by default it displays last 10 lines 
   ex : tail filename
   ex : tail - n 4 filename -- it displays last 4 lines of a file

* more - used to display content of a file in large format
  ex : more filename

* less - used to search features is provided
       - do not load entire file at a time
  ex : less filename             
    
File Changing Permissions:
=========================

-- Permissions for a file is used to secure the file

-- Linux file permissions :
   > read (r)     = access to data
   > write (w)    = change or modify data of a file
   > executive(x) = we can run or execute the file

-- Permissions are given to three sets of people: 
   > owner(u)  = creates a file 
   > group(g)  = every file and folder has its own associated with its group
   > others(o) = any of users that are not part of owner and group

-- Two methods to change permissions:
   1. using operators:
     '+' = add a permission 
     '-' = remove a permission 
     '=' = replicate permission 
      ex : chmod u+r filename
           chmod g-w filename
           chmod o=x filename
           chmod a+r filemane - this commnand give permissions at a time to three sets of people(u,g,o)
   2. using numerators:
      '1' = exectution permission 
      '2' = write permission 
      '4' = read permission
       ex : chmod 751 filename

User Mangement:
==============

-- adding users & deleting users

* adduser is standard like giving all iformation 
   ex : sudo adduser username
        sudo adduser -u 2023 username --mentioned user id
        sudo adduser -e 2022-4-5 username --specify expiry date

* userdel command used to remove user 
   ex : sudo userdel username 
        sudo userdel -r username --delete users home directory
        sudo userdel -r -f username --delete user others files in othet location

-- adding groups & deleting groups

* groupadd is used to create new group 
   ex : sudo groupadd groupname
        
* groupdel is used to delete group 
   ex : sudo groupdel groupname

-- how does linux os adduser:
   controller wil edit the following files for newuser account

* cat /etc/passwd - infomation about users
* cat /etc/shadow - passwords of users
* cat /etc/group  - informstion about group 
* cat /etc/gpasswd- passwords of groups

Finding Stuff:
=============

* locate - used to find / search files 
  ex : locate filename

* whereis - used to find binary files and also prints for a man page
* which   - returns the location of binaries in path variable
* echo $ PATH - used to display the path of the url  
* find    - used to find/ search files
  ex : find filename
* grep    - used to search through the file ,looking for matches to the pattern specified 
  ex : grep 'word'filename

Process Management:
==================

* ps - used to display the current running process
  ex : ps 
       PID TTY  TIME CMD

* ps -e - used to display daemons
  ex : ps -e
       PID TTY TIME CMD

* ps -f - used to display current running process with options
  ex : ps -f 
     UID PID PPID C STIME TTY   TIME CMD

* ps-aux - list all running process in linux os 
  ex : ps aux 
      USER PID %CPU %MEM VSZ RSS TTY

* fg - bring most recent job to foreground
 
* bg - list stopped/blocked jobs in the background

* job - used to display jobs/process that are running or suspend in background

* top - used to display the dynamic real time of the running process
  ex : top
       PID USER PR NIC VIRT RES %CPU %MEM COMMAND

* kill - used to stop running process and also used to way of communicate a process 
       - its suspend, terminate, stop, break, pause, restart, continue
   ex : kill -l 
       

Software Management:
====================

-- It is used to install/removed third party software

-- searching for a package
*  sudo apt -cache search software

-- adding a software
*  sudo apt -get install software

-- removing a sofrware
*  sudo apt -get remove software

-- update apackage
*  sudo apt -get update

-- upgrade software
*  sudo apt -get upgrade

Network Management:
==================

* ifcongif - used to dispaly the system network interface information
    
* hostname - used to display machine hostname

* netstat -l - used to display all listening ports

* netstat -t -used to dispaly all TCP connections

* ping - used to know our machine is able  comminicate or not with server
  ex : ping google.com
       ping -c 4 google.com

* whois - used to display domain 

* ethtool - to get the details about network interfaces 

* if up etho - used to bring up network interfaces

* if down etho - used to bring down network inteerfaces

* traceroute - used to network troubleshoot
  ex : traceroute -4 ipv4

* curl - used to access our website through cli

* nslookup - used to dispaly DNS information
  ex : nslookup google.com
       name :
       address:

* dig domain - used to get DNS with more information for domain
  ex : dig domain 

* dig -x domain -reverse lookup host

* wget - the wget is the free non-interactive file download , can work in back ground when user to get disconnected with the system    while wget finish its work 
  ex : wget file
       wget -c file -- continue stopped download
       wget -r curl --recursively download files from curl

* env - used to display your current environment or run a specified command in a changed environment
  ex : env

* export - used to mark variables and functions to be passed to child process
  ex : export

*crontab - dispaly a list of commands that you want to run on a regular schedule

* tar - used for saving several files into an archive
  ex : tar cf file.tar file -- tar files into the file.tar
       tar xf file.tar file -- untar into the current directory
       tar tf file.tar file -- show contents of archive         

* zip - used to compress and archive data
  ex : gzip filename

* unzip - used to decompress and extract the content from the compress archived
 ex : gunzip filename

* http - http stands for a hypertext transfer protocol used for transferring data over a network ,includes website content and API calls ,uses http protocol. There are two main kinds of http messages: request and responses.

* https -The S in https stands for secure. Https uses TLS(SSL) to encrypt normal  http requests and responses.As a result ,https is far more secure than http.

* internal network - An internal network , called an intranet , is one which is restricted to a difined set of users.An example would be a network accessed only by the employees  of a specific company.

* external network - An external network allows users of all types access. Besides the internet, an example would include a network that allows customers to connect s company to place orders.

* public subnet - Instances in public subnet can connect directly to internet through an nternet gateway 

* private subnet - Instances in private subnet can connect to the interne using a network address translation (NAT) gateway,but cant receive unsolicited inbound connections from internet.

* TCP - TCP means transmission control protocol , is a connection based protocol while tcp is more reliable,it transfers data more slowly .

* UDP - UDP means user datagram protocol ,is a connectionless. UDP is less reliable but works more quickly.

* System Info:
=============

* date - used to display current date/time

* cal - used to display months calender

* uptime - show uptime

* whoanmi - display who are you logged in as

* uname -a - show kernel config 

* man - show documentation of tool ,command, software

* du - show disk usage space 

* df - show disk free space

* diff - show difference between files

* wc - used to find out number of lines ,word count,byte and characters count in the files specified in the file arguments
 ex : wc [option] filename

* SSH secure shell:
===================

-- which is used to remotely connect and control others devices 

* service ssh status -display the status of shell

* service ssh start - used to start the shell 

* service ssh stop - used to stop the shell

* service shh restarts - used to restart the shell

* ssh user@host - connect to host as user

* scp - scp means secure transferring computer files between a local host and a remote host or between two remote hosts.
  

DOCKERE COMMANDS:
=================

* docker built -t name -build an image from the dockerfile in the current directory and tag the image

* docker images - list all images

* docker rmi id/name - remove the image

* docker create image - its create the container

* docker run image - its create the container and give response

* docker rename old container name new container name - its rename the container name

* docker container prune - used to remove all the stoped containers are present

* docker rm containername/id - remove the container

* docker rm containername/id -f - remove contianer force fully

* docker ps -a - list the containers

* docker container ls - list the containers

* docker start containername/id - starts the container

* docker stop containername/id - stop the container

* docker restart containerid/name - restart the container

* docker container commit containername imagename - it creates the image by using container

* docker exec -it container bash - connect to the container

* docker wait containername - it blocked the container

* docker kill container - it kills the container

* docker pull <image-name> -  pull an image from a registry

* docker push image - push an image to a registry

* docker login - used to login into docker hub

* docker push image - push the image to dockerhub

* docker info - get infomation of docker tool

* docker history image - display history if an image with the image name mentioned in the command

* docker volume ls - display the volumes

 DOCKER SWARM :
================

* docker swarm init - used to initialized the docker container

* docker swam join --token position, details - to join the node into the swarm

* docker node ls - list the nodes

* docker swarm leave -f - used to left the node

* docker-compose -version - display the version

* docker-compose up - run our docker compose file

* docker-compose dockerfile up - used to run particular mentioned compose file


Git:
===
-- It is a version control system(VSC)  or source control system .
-- It is a platform independent.
-- It is used for track the changes in a file.
-- It is free and open souce .
-- They can handle largh projects efficiently.

Git Stages:
========== 
-- Working Directory 
-- Storing area
-- Rrepository 

* Working directory:
---------------------
-- In this stage git is only aware of having files in the project .
-- Modified means that you changed the file but have not committed.

* Staging area:
---------------
-- The staging area is like rough draft space, its where you can git add the version of file.

* Repository:
-------------
-- A repository has all the project related data.
-- It contain all collection of the files and also history of changes made to those files.

Types of Repos:
==============
-- Local repository
-- Central repository
-- Remote repository 

Git installation:
=================
-- sudo update
-- sudo apt-get install git

* Configuration user:
--------------------
-- username  : git config user.name "username"
-- e-mail id : git config user.email "email"

* Git Commands:
---------------
-- git init                       : create empty git repository 
-- git status                     : it displays the nimber of files(untracked files, tracked files and deletes files)
-- git add filename               : it tracks the file
-- git add .                      : it tracks all files in working directory ("." = all files) 
-- git restore  --staged filename : it untracks the file
-- git restore  --staged .        : it untracks all the files ("." = all files)
-- git commit -m "any message"    : push the files to remote repository 
-- git log                        : to see the committed files (and also stores committed files after it deleted)
-- git remote add origin url      : To verify that the remote repo was added to your configuration
-- git push origin branch         : that pushes a local branch(es) to a remote repository (origin)
-- git remote -v                  : This command will show that GitHub is the fetch and push targets of the local repository

*Ignoring Content:
------------------
-- It will be useful when you don't want to track some specific files then we use a file called ".gitignore".
-- vi .gitignore 

* Git branches :
---------------
-- A branch represents a independent line of development.
-- The git branch command lets you are create , list, rename and delete.
-- The default branch name in git is 'master'.
*  git branch                           : to see current branch  
*  git branch 'branchname'              : to add a new branch 
*  git checkout branch name             : to switch branches
*  git checkout -b branch name          : to create and switch at a time to branch 
*  git branch -m old name new name      : to rename a branch
*  git branch -d branch name            : to delete a branch 
-- use '-D' instead if you want to force the branch to be deleted
*  git restore filename                 : restore deleted files
*  git push origin --delete branch name : it deletes branch from remote repository

* Git Tags:
------------
-- git tag                      : to see current tag
-- git tag name(v1.0)           : to create new tag
-- git tag -a name  -m "message": create and allotated message  at a time to tag
-- git show tag name            : to display infomation about tag( version ..)
-- git push origin tagname      : push local to remote
-- git push origin --tags       : The command pushes all local tags to the specified origin repository

*Git merging:
-------------
-- Merging is Git's way of putting a forked history back together again.
-- To merge branches locally, use git checkout to switch to the branch you want to merge into. This branch is typically the main      branch. Next, use git merge and specify the name of the other branch to bring into this branch.
*  git checkout branch : to swtich the branch (destinaation branch)
*  git merge branch    : merging files (source branch)

*Git cloning:
-------------
--git clone is primarily used to point to an existing repo and make a clone or copy of that repo at in a new directory, at another location.
*  git clone url
*  git clone -b branch name url : to clone from particular branch
*  git pull origin branch name  : fetches commits from the master branch of the origin remote (into the local origin/master  branch)    and then it merges origin/master into the branch you currently have checked out. `git pull` only works if the branch you have checked out is tracking an upstream branch.






