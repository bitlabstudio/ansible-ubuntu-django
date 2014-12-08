# Ansible Playbook for Django on Ubuntu 12.04

STATUS: Playbook contains untested changes!

## Overview

This is an Ansible playbook that sets up a Ubuntu 12.04 machine as a server
for a Django project.

* PostgreSQL as the database
* nginx & uWSGI to serve the Django site
* Supervisor to daemonize uWSGI

## Prerequisites

We assume that you have created your Ubuntu instance and that you are given a
root password. First you want to upload your public RSA key so that you don't
need that root password any more. Secondly we need to create a user `django`.

If you are on OSX, you need to install sshpass:

```
curl -O -L http://downloads.sourceforge.net/project/sshpass/sshpass/1.05/sshpass-1.05.tar.gz
tar xvzf sshpass-1.05.tar.gz
cd sshpass-1.05
./configure
make
sudo make install
```

* Add all keys that should have access to the server to `/roles/prerequisites/templates/authorized_keys`
* Create your `vars/external_vars.yml` file and generate all necessary
  passwords and variables
* Run `ansible-playbook -i hosts prerequisites.yml --ask-pass`
* SSH into the server `ssh django@IP`
* Add the user's key to your Github profile: `cat ~/.ssh/id_rsa.pub`

Now you should be able to SSH into the server as `root` and `django` without
entering a password.

## Usage

To execute the playbook:

    ansible-playbook -i hosts server.yml
