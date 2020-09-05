---
layout: post
title:  "Blog0"
date:   2020-09-04 20:24:31 -0700
categories: jekyll update
---
#How to install Apache server in CentOS 7#

Note:
 Apache is available with CentOS7 default repository which we can use `yum` package manager to install it. 
 `firewalld` needs to be installed prior to installing Apache.

==>Installing Apache<==

Step one:  Update the local Apache `httpd` package by running the following command:

`sudo yum update httpd`

Step two: Install Apache package by using `yum` command:

`sudo yum install httpd`  

- Note: yum will install all the Apache dependencies.

Step three: Open up port 80 to allow incoming http and https requests:
 
`sudo firewall-cmd —permanent —add-service=http`
`sudo firewall-cmd —permanent —add-service=https`

Step four: Reload the firewall update the newly added rules:

`sudo firewall-cmd —reload`


==>Checking the web-server<==

In this section we will run the service and check the initial page.

Step one: Run the httpd service after the installation:

`sudo systemctl start httpd`

Step two: Check the service status and verify that the service is running:

`sudo systemctl status httpd`

Step three: Test the default website by typing the host IP:

`http://Server_IP`


==>Managing Apache Process<==

In this section we will list the basic command whcih we will need in the future:

to Stop and start httpd service:
`sudo systemctl stop httpd`
`sudo systemctl start httpd`

To stop and start agian:
`sudo systemctl restart httpd`

To enable and disable the Apache service:
`sudo systemctl enable httpd`
`sudo systemctl disable httpd`


