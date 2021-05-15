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
	$ cd WAS-Install

	• Update your inventory, e.g:
	$ vim hosts
	[dmgr_host]
	192.168.10.20 ansible_host=192.168.10.10

	• Update variables in playbook file - Set WAS cluster, cell, appname , contextroot variables
	$ vim was-app-install.yml
	- name: WAS deployment playbook
	  hosts: was-nodes       # Inventory hosts group / server to act on
	  become: yes               # If to escalate privilege
	  become_method: sudo       # Set become method
	  remote_user: {{ was_user }} # Update username for remote server
	  vars:
	    was_command_path: opt/IBM/webshere/bin/wsadmin.sh       # WAS commands script path(you will get it on DMGR after product installation )
	    was_user: wasusr                                        # User with which product is installed
	    console_user: wasadm                                    # User to login into WAS console
	    console_pass: admin                                     # WAS console passwrd
	    cellname: appcell                                  
	    appname: app1
	    clustername: appcluster
	    backup_path: /tmp/backup/{{ appname }}   
	    ear_filename: app1.ear
	    earfile_path: 
	  roles:
	    - was-app-install

