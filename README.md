# Ansible Playbook for Django on Ubuntu 12.04

DO NOT USE THIS! PLAYBOOK NOT EXECUTABLE! WORK IN PROGRESS!

## Overview

This is an Ansible playbook that sets up a Ubuntu 12.04 machine as a server
for a Django project.

* PostgreSQL as the database
* nginx & uWSGI as webservers
* Supervisor to daemonize uWSGI

## Prerequisites

* Add your public key to `/root/.ssh/authorized_keys`
* As root, run `adduser django`
* Add your public key to `/home/django/.ssh/authorized_keys`
* As django, run `ssh-keygen -t` and add that key to your private repo on
  Github.

## Usage

To execute the playbook:

    ansible-playbook -i hosts server.yml
