## Vi

[virtualization](https://www.simplilearn.com/benefits-of-virtualization-in-cloud-article)
![](../virtuaization/images/click-new1.PNG)
![](../virtuaization/images/name-of-the-vm-2.PNG)

![](../virtuaization/images/memory-allocation-3.PNG)

![](../virtuaization/images/vrtual-disk-4.PNG)

- To download centos7 iso, click on this link [centos7 iso](http://isoredirect.centos.org/centos/7/isos/x86_64/)

- then click on :
  ![](../virtuaization/images/centos7-iso-link.PNG)

- Then, download this:
  ![](../virtuaization/images/download-centos.PNG)

### To install the centos OS:

- click on settings:
  ![](../virtuaization/images/centos-os-1.PNG)

![](../virtuaization/images/storage-2.PNG)

- choose the downloaded centos7 iso:
  ![](../virtuaization/images/downloaded-file-3.PNG)

- check the CD/DVD box and click ok:
  ![](../virtuaization/images/chek-cd-4.PNG)

- click on network and attach adapter
  ![](../virtuaization/images/network-5.PNG)

## the same step will be repeated for ubuntu, but it will be ubuntu(64bit) instead of redhat(64bit)

## How to install Vagrant on VM automatically

- create a directory
  `mkdir vagrant-ms`

- cd into the directory

`cd vagrant-ms`

- create a direcory named centos7 or any name

`mkfir centos7`

- create another directory name ubuntu18 or any name of your choice

`mkdir ubuntu18`

- cd into centos7

`cd centos7`

![](../virtuaization/images/Centos-auto.PNG)

![](../virtuaization/images/geerlin.PNG)

- write this command below
  `vagrant init geerlingguy/centos7`

![](../virtuaization/images/vagrant-init.PNG)

![](../virtuaization/images/installed-success.PNG)

- run vagrant bup to run the vagrant
  `vagrant up`

![](../virtuaization/images/vagrant-up.PNG)

- you can do the command below to login into the vagrant
  `whoami`
- To see the working directory run:
  `pwd`
- To list out filea in the current directory, you run
  `ls`

- To read a file, run cat command
  `cat /etc/os-release `

- To switch to root user
  `sudo -i`
  ![](../virtuaization/images/commands.PNG)

- forward slash (/) means root directory
  ![](../virtuaization/images/sample.PNG)

- To make directory, run
  `mkdir nameof dir`

- to make file, run:
  `touch nameof file`
  ![](../virtuaization/images/makefile.PNG)

- To copy one directory to another directory, run:
  `cp -r`

- To set number in linux run
  `:se nu`
  ![](../virtuaization/images/number.PNG)

- To navigate to the first line, run
  `gg`

- To naviagate to the last line run,
  `shift + g`

- To copy in linux run on the line
  `yy`

## FILER AND IO REDIRECTION COMMANDS

- To search for content i files,run
  `grep`

- To disable the case sensitivity, run
  `grep -i`

- To ensure the grep command get into directory, run
  `grep -iR `

![](../virtuaization/images/reidrection.PNG)

- To avoid searching for a particular word,run
  `grep -vi`

![](../virtuaization/images/grep.PNG)

- To paste above run
  ` P`
- To paste below run
  `p`

- If you want to copy multiple lines like 4 lines run:
  `4 yy`

- To delete run
  `dd`

- To undo ,use
  `u`

- to count number of lines run
  `wc -l /etc/paswwd `
  ![](../virtuaization/images/count-lines.PNG)

- to count the no of files in etc, first cd into etc, then run
  `ls | wc-l`
  ![](../virtuaization/images/files-count.PNG)

- to search for files that start with host in etc, run
  `ls | grep host`
  ![](../virtuaization/images/hostfiles.PNG)

- standard ouput redirection
  ` ls >> /etc/passwd`
  ![](../virtuaization/images/so.PNG)

`uptime > /tmp/sysinfo.txt`
![](../virtuaization/images/correct-redirect.PNG)

- if you dont want to see any output in a file, you can reidret it to dev/null
  `yum install vim -y /dev/null`

- if you want to redirect standard error to a file,add 2
  ` free -m 2 > /tmp/error.log`
  ![](../virtuaization/images/error.PNG)

- go get any type of output, including standard error use '&'
  `freeee -m &>> /tmp/error.log`
  ![](../virtuaization/images/anyoutput.PNG)

### PIPING

- to count the no of files in etc, first cd into etc, then run
  `ls | wc-l`
  ![](../virtuaization/images/files-count.PNG)

- to search for files that start with host in etc, run
  `ls | grep host`
  ![](../virtuaization/images/hostfiles.PNG)

- To search if there is vagrant in the laxt 20 files of /var/log/messages, run
  `tail 20 /var/log/messages | grep -i vagrant`
  ![](../virtuaization/images/piping.PNG)

## find command

- to find any files, you can use file command
  `find /etc -name host*`

## USERS AND GROUPS

- to add users, run useradd aomand
  `useradd ansible`
  `useradd jenkins`
  `useradd aws`
  ![](../virtuaization/images/useesadd.PNG)

- to create group, run
  `groupadd devops`
  ![](../virtuaization/images/groups.PNG)

- to create passwd, run passwd and the name of the group
  ![](../virtuaization/images/passwd.PNG)

- to switch from rootuser to a regular user run su -name of rhe user
  `su -ansible`
  ![](../virtuaization/images/pass.PNG)

- ro delete user, run userdel command
  `userdel -r aws`
  `userdel -r jenkins`
  `userdel -r ansible`

- to remove group run groupdel
  `groupdel devops`
  ![](../virtuaization/images/groupdel.PNG)
  ![](../virtuaization/images/history.PNG)

- to add a user to a particular group run:
  `usermod -aG nsmeofgroup nameofuser`

### FILE PERMISSIONS

- to change ownership ,run chown command:
  -to change the ownership recursively i.e to all subdirectories inside the file,add R
  `chown -R ansible:devops /opt/devopsdir`
  ![](../virtuaization/images/changeownership.PNG)

- to remove executable permission from others,run:
  `chmod o-x`

-to add write permission to group(symbolic), run:
`chmod g+w `
![](../virtuaization/images/permission.PNG)

- if you want to change permission numerically:
  `chmod 770 /opt/webdata`
  ![](../virtuaization/images/numerucal.PNG)

### SUDO

- Sudo gives power to normal users to execute commands which is owed by root user
- to set your file to have root privileges cd into
  `cd /etc/sudoers.d`
  ![](../virtuaization/images/sudo.PNG)



### SOFTWARE MANAGEMENT

- TREE COMMAND
![](../virtuaization/images/tree.PNG)

- yum automates all packages it is located in /etc/yum.repos.d

- steps to install jenkins on centos7
`sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo`
- the code above will create a file named 'yum.repos.d/jenkins.repo

`sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key`
- helps get key to get access to the repository

`sudo yum upgrade`

``