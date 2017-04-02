###################################################
Ansible configuration file used for managing Cloud1
###################################################

This Ansible project was created to cover this things:

* Manage Cloud1 floating IPs
* Allow to delete all servers belonging to specific user (based on prefix)
* Add new user accounts and ssh keys in Bastion server which allows us to spare
  IPv4 addresses.

How to delete all servers based on prefix
=========================================

Ansible playbook contains special role **servers** which allow us to delete all
servers belonging to specific user. The whole procedure is based on the prefix
so always be sure that you will not delete someone elses servers by specifying
too short prefix.

Command required to execute the operation::

   ansible-playbook site.yml -t blacklist -e prefix=$SOME_PREFIX

Where **$SOME_PREFIX** should be a variable holding info about the prefix which
will be used to delete the server.
