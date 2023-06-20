Ansible Debian Sury role
========================

[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-HanXHX.debian_sury-blue.svg)](https://galaxy.ansible.com/HanXHX/debian_sury) ![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/hanxhx/ansible-debian-sury/molecule.yml?branch=master)

Install [Sury repository](https://deb.sury.org/) for Debian.


Managed OS / Versions
---------------------

|          OS          |       Status        |
|:--------------------:|:-------------------:|
|  Debian Buster (10)  | :heavy_check_mark:  |
| Debian Bullseye (11) | :heavy_check_mark:  |
| Debian Bookworm (12) | :heavy_check_mark:  |


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

```yaml
- hosts: servers
  gather_facts: yes
  roles:
     - { role: HanXHX.debian-sury }
```

License
-------

GPLv2

Donation
--------

If this code helped you, or if you’ve used them for your projects, feel free to buy me some :beers:

- Bitcoin: `1BQwhBeszzWbUTyK4aUyq3SRg7rBSHcEQn`
- Ethereum: `0x63abe6b2648fd892816d87a31e3d9d4365a737b5`
- Litecoin: `LeNDw34zQLX84VvhCGADNvHMEgb5QyFXyD`
- Monero: `45wbf7VdQAZS5EWUrPhen7Wo4hy7Pa7c7ZBdaWQSRowtd3CZ5vpVw5nTPphTuqVQrnYZC72FXDYyfP31uJmfSQ6qRXFy3bQ`

No crypto-currency? :star: the project is also a way of saying thank you! :sunglasses:

Author Information
------------------

- Twitter: [@hanxhx_](https://twitter.com/hanxhx_)
