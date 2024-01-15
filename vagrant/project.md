### Sync Directories

### Hosting a website

#### step 1 - go to [tooplate](https://www.tooplate.com/view/2121-wave-cafe) to pick any html page you link

#### navigate to vagrant-ps and create a directory and run vagrant init plus name of the box to have vagrantfile in the directory

![vagrantfile](../vagrant/images/vagrantfile.PNG)

- we need  ip address to assess our website, so we edit the vagrantfile in vim editor
![vagrantfile](../vagrant/images/vi-vagrantfile.PNG)

- run vagrant up
![vagrant up](../vagrant/images/vagrant%20up.PNG)

- run vagrant ssh, then install the packages by running
`yum install wget unzip -y`

- run
`systemctl start httpd`
`systemctl enable httpd`

- to access the default page, you need your ip adrress, either static or public ip address, to get ip address , run this command

`ip addr show`
![ip-address](../vagrant/images/ip-address.PNG)
- if you paste the ip address on any browser, it should show you something like this

![apache-test-site](../vagrant/images/testing-site.PNG)


- since server data is located in /var directory, hence put your html templates or files in this directory

`cd /var/www/html`

- in this directory, open index.html file with vi editor and type some text in it

![index-html](../vagrant/images/index-html.PNG)

- Then restart your server
`systemctl restart httpd`
![restart-httpd](../vagrant/images/restart-httpd.PNG)

![httpd-site-now](../vagrant/images/htttpd-site-now.PNG)

- To download our wavecafe html template on our machine, cd in to tmp directory and run
`wget https://www.tooplate.com/download/2121_wave_cafe `

![zipped](../vagrant/images/zpped.PNG)
- Bevause the downloaded file is in zipped mode, run unzip command to unzip it
![unzipped](../vagrant/images/unzipped.PNG)

- Take a look at what the unzipped file look like
![unzipped-wavecafe](../vagrant/images/unzipped-wavecafe.PNG)


- then copy the files and directories inside the /tmp/21-21_wave_cafe into /var/www/html

`cp -r * /var/www/html`

- Restart your server

`systemctl restart httpd`

- confirm if the file copied successfully to /var/www/html

`ls /var/www/html`
![confirm-success](../vagrant/images/confirme-copy-succesfully.PNG)

![httpd-status](../vagrant/images/httpd-status.PNG)

- refresh the apache site and it should look like this
![hosted](../vagrant/images/host-site.PNG)



#### VARIABLES

![variable](../bashscripting/images/variable.PNG)