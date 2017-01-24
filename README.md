# Ansible Playbook for Django on Ubuntu

STATUS: Playbook contains untested changes!

## Overview

This is an Ansible playbook that sets up a Ubuntu 14.04 machine as a server
for a Django project.

* PostgreSQL as the database
* nginx & uWSGI to serve the Django site
* Supervisor to daemonize uWSGI

## Prerequisites

We assume that you have created your Ubuntu instance and that you are given a
root password. Depending on what you prefer you first want to upload your
public RSA key or make use of a .pem file so that you don't need that root
password any more.

## Usage

* Create your `vars/external_vars.yml` file and generate all necessary
  passwords and variables
* Add all keys that should have access to the server to
  `/roles/access/templates/authorized_keys` (only if you want to upload your
  keys)

To execute the playbook:

    ansible-playbook -i hosts server.yml
