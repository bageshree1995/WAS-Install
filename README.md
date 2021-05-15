# WAS-Install
# Role info

Ansible Role to install application on IBM websphere application server.

# Tasks in the role
	This role contains tasks to:
	• Stop the application on WAS console.
	• Backup the existing application.
	• Check whether application needs to newly install or just need to update.
	• Based on the above condition install or update the application.
	• Check if application is distributed on all the nodes.
	• Start the application on WAS console


![image](https://user-images.githubusercontent.com/78317929/118358903-8e317c00-b59e-11eb-9f76-b8204269193f.png)

# How to use this role

	• Clone the Project:
	$ git clone https://github.com/bageshree1995/WAS-Install.git
	$ cd tomcat-ansible

How to use this role
Clone the Project:
$ git clone https://github.com/jmutai/tomcat-ansible.git
$ cd tomcat-ansible

$ vim hosts
[tomcat-nodes]
192.168.10.10

