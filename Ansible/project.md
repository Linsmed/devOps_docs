#ANSIBLE

- create a four vms, ansible, srv01, srv02, srv03 using vagrant and install ansible on the ansible vm.
# To install ansible, run the following commands
`sudo apt update`
`sudo apt-add-repository ppa:ansible/ansible`

`sudo apt update`
`sudo apt install ansible`
![ansible](../Ansible/image/ansible-installed.PNG)

- to check the version of ubuntu running, run

`lsb_release -a`

![lsbl](../Ansible/image/lsbl.PNG)


- We have to create a user on other three vms. Vagrant ssh into srv01 and create a user named devops and grant the user the sudo privileges

`useradd devops`

`passwd devops`

`visudo`
![visudo](../Ansible/image/VISUDO.PNG)


- We need to check the /etc/ssh/sshd_config file to check the password authentication,let the passwordauthentication be yes

`vi /etc/ssh/sshd_config`
![password](../Ansible/image/passsword.PNG)

- After the change, you need to restart the service

`service sshd restart`

![service](../Ansible/image/service.PNG)

- Then do the same process for other servers too i.e srv02,srv03

- for srv02(srv01,srv02 which is redhat,run useradd to add a user, and the service name is sshd, that is why we run service sshd restart)
![srv02](../Ansible/image/srv02.PNG)

- for srv03, which is an ubuntu, the service name is ssh instead of sshd in Redhat 

`adduser devops`
![srv03](../Ansible/image/srv03.PNG)

`passwd devops`

`export EDITOR=vim`


`visudo`

![visudo](../Ansible/image/srv03.PNG)

-edit the configuration file /etc/ssh/sshdconfig and passwordaunthentication should be yes

![pass](../Ansible/image/srv03-pass.PNG)

`service ssh restart`

- Now , let us login back to the ansible machine and try to ssh into the linux machines created(srv01,srv02.srv03)


`vagrant ssh ansible`

`ssh devops@192.168.5.3`
![ansible](../Ansible/image/ansible-ssh-srv01.PNG)

 - for srv02

 `ssh devops@192.168.5.4`

 - for srv03

 `ssh devops@192.168.5.5`

 ![ansible-ssh](../Ansible/image/ansible-ssh-srv02.PNG) 