Ansible Debian Sury role
========================

[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-HanXHX.debian--sury-blue.svg)](https://galaxy.ansible.com/HanXHX/debian-sury) [![Build Status](https://travis-ci.org/HanXHX/ansible-debian-sury.svg?branch=master)](https://travis-ci.org/HanXHX/ansible-debian-sury)

Install Sury repository for Debian

Requirements
------------

None.

Role Variables
--------------

- `sury_apt_url`

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: HanXHX.debian-sury }

License
-------

GPLv2

Author Information
------------------

- Twitter: [@hanxhx_](https://twitter.com/hanxhx_)
