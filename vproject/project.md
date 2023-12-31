### Multi tier web application stack
### setup on laptop/desktop
### Tools
- Hypervisor -oracle vm virtualbox
- Automation -vagrant
- CLI -gitbash
- IDE - sublime text

#### Architecture of project services
- NGINX
- TOMCAT
- RABBITMQ
- MEMCACHED
-  MYSQL

### Architecture of automated setup
- vagrant
- virtualbox
- gitbash

- Before you bring up the vagrant, you must install all these
-  vagrant plugin install vagrant-hostmanager
- vagrant plugins install vagrant-vbguest
![plugin](../vproject/images/plugin.PNG)


### step 1 - clone the repository

![](../vproject/images/cd-manual.PNG)

- run vagrant up
`vagrant up`
- ssh into webo1 and confirm connectiviity by running
`ca /etc/hosts`

- then run:
`ping app01`
![ping](../vproject/images/ping.PNG)

- all the 5 vms will be running by now
- vagrant ssh into db01, switch to root user and run
`yum update -y`
![update]()

- run this command
`yum install epel-release -y`
![epel](../vproject/images/epel.PNG)

![](../vproject/images/profile.PNG)

- run this command to make it permanent

`source /etc/profile`


- run:
`yum install git mariadb-server -y`

![mariadb](../vproject/images/mariadb.PNG)

- Check if mariadb is active

`systemctl status mariadb`
![mariadb](../vproject/images/mariadb-status.PNG)

- set up mysql root password
![mysql-secure](../vproject/images/mysql-secure.PNG)

- run thus command and enter the password earlier set
`mysql -u root -p`
![pass-mariadb](../vproject/images/pass-mariadb.PNG)

- clone into the source repository

` git clone -b local-setup https://github.com/devopshydclub/vprofile-project.git`

![cloned](../vproject/images/Cloned.PNG)

- database
![database](../vproject/images/database.PNG)



### step 2
- switch to mc01, switch to root user and run:
`yum update -y`
![update](../vproject/images/memcache-update.PNG)

- install epel release package
`yum install epel-release -y`
![epel](../vproject/images/epel-memcach.PNG)

- install memcached
`yum install memcached -y`
![memcached](../vproject/images/memcached-install.PNG)

- run the following commands
`systemctl start memcached`
`systemctl enable memcached`
`systemctl status memcached`
![memcached-status](../vproject/images/memcached-status.PNG)

- for memcached to listen to tcp and ucp ports,run

`memcached -p 11211 -u 11111 -u memcached -d`

- to verify if it listens on the port, run
`ss -tunlp | grep 11211`
![verification](../vproject/images/verification.PNG)



### step 3
- ssh into rmq01, switch to root user and run
`yum update -y`
![](../vproject/images/rm-update.PNG)


- Install Dependencies
`yum wget -y`
`wget http://packages.erlang-solutions.com/erlang-solutions-2.0-1.noarch.rpm`

`sudo rpm -Uvh erlang-solutions-2.0-1.noarch.rpm`
![rabbitmq](../vproject/images/rabbitmq.PNG)

`curl -s https://packagecloud.io/install/repositories/rabbitmq-server/script.rpm.sh | sudo bash`
![rabbit](../vproject/images/reposi-rabbitmq.PNG)

- install rabbitmq server
`sudo yum install rabbitmq-server -y`
![rabbit-server](../vproject/images/rabbit-server.PNG)

`sudo systemctl start rabbitmq-server`
`sudo systemctl enable rabbitmq-server`
`sudo systemctl status rabbitmq-server`
![rabbit-status](../vproject/images/rabbit-status.PNG)

#### Setup access to user test and make it admin

`echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config`
`sudo rabbitmqctl add_user test test`
`sudo rabbitmqctl set_user_tags test administrator`
`sudo systemctl restart rabbitmq-server`
`sudo systemctl status rabbitmq-server`
![config-rabbit](../vproject/images/config-rabbit.PNG)

#### step 5
- login into app01 and run yum update -y
- switch to root user 
`sudo -i`

- install epel-release 
`yum install epel-release -y`
- go to tmp directory and download tomcat

` wget https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.75/bin/apache-tomcat-9.0.75.tar.gz`

![tomcat](../vproject/images/tomcat.PNG)

- extract the file
`tar xzvf apache-tomcat-9.0.75.tar.gz`

- Add tomcat user

` useradd --home-dir /usr/local/tomcat --shell /sbin/nologin tomcat`

![tomcatdir](../vproject/images/tomcat-dir.PNG)

- copy the files to tomcar
`cp -r /tmp/apache-tomcat-9.0.75/* /usr/local/tomcat/`

![](../vproject/images/tomcat-copy.PNG)

- Make tomcat user owner of tomcat home dir

`chown -R tomcat.tomcat /usr/local/tomcat`
![ownership](../vproject/images/ownership.PNG)

- Create tomcat service file

`vi /etc/systemd/system/tomcat.service`
` systemctl daemon-reload`
`systemctl start tomcat`

`systemctl enable tomcat`
![](../vproject/images/tomcat-status.PNG)


