playbook-ohie-fr
================

Ansible playbook for deploying the facility registry component of the [OpenHIE](http://ohie.org) stack.
**Note:**For the debian package go [here.](https://bitbucket.org/instedd/resource_map/wiki/Install%20&%20Update)

## What it does
* Installs prereq packages
* Sets up resourcemap

## Requirements
* Ansible **1.2+** installed on client.
* Debian based distro installed on target machine (tested with Ubuntu 12.04 LTS).
* root username/password on target machine, ssh installed and running.
* **If you do not having the required python packages uncomment the `# - bootstrap` line in the `site.yml` file.**

## Vars and setup
You will need to copy `group_vars/all.example` to `group_vars/all` then edit the variables in`group_vars/all`. Make sure to put in the correct fqdn or ip for this server.

Also copy `hosts.example` to `hosts` and enter the ip or hostname of your server in place of the ip.

By default we try to login with root via ssh, if you have another user with sudo access on your server(e.g. AWS) edit `site.yml` and change the user and uncomment the sudo line.

## Running the play
`ansible-playbook -k -i hosts site.yml`

Drop the -k if you are logging in with a public/private key. 

`ansible-playbook -i hosts site.yml`

After this is complete(May take a few minutes) point your browser to http://ip_or_hostname and register a new accounut.
