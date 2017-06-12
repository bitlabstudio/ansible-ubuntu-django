# Ansible Playbook for Django on Ubuntu

## Overview

This is an Ansible playbook that sets up a Ubuntu 16.04 machine as a server for a Django project. It is primarily built for a typical AWS or Digital Ocean server.

* PostgreSQL as the database
* nginx & uWSGI to serve the Django site
* Supervisor to daemonize uWSGI

## Prerequisites

* Set up a AWS or Digital Ocean server
* Add all needed SSH keys to the server
* Add the server IP address to 
    * the ansible hosts file `hosts`
    * and the variables: file `vars/external_var.yaml`

#### Let's Encrypt

You'll have to change the A-records of your domain before running the letsencrypt roles. Otherwise letsencrypt is not able to verify your site.

## Usage

Install Ansible: http://docs.ansible.com/ansible/intro_installation.html#installation

Create your `vars/external_vars.yml` file and generate all necessary passwords and variables.

Run the ansible-playbook script:

    ansible-playbook -i hosts server.yml

If you want to start over beginning at another task, use:

    ansible-playbook -i hosts server.yml --start-at-task="task name"
