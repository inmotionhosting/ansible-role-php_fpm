inmotionhosting.php_fpm
=========

Modular Ansible Role for deploying and configuring PHP-FPM

[![Build Status](https://travis-ci.org/inmotionhosting/ansible-role-php_fpm.png?branch=master)](https://travis-ci.org/inmotionhosting/ansible-role-php_fpm)

Requirements
------------

* CentOS 7.x or later
* Debian 9 or later
* Ubuntu 16.04 LTS or later

Role Variables
--------------
In this role, we load the defaults and then modify them as needed to
support other platforms.

### Defaults
This role uses [defaults/main.yml] to declare "global" variables using
CentOS 7.x as our base.  This allows defining a core set of variables
that can be trivially modified.

[defaults/main.yml]: https://github.com/inmotionhosting/ansible-role-mysql/blob/master/defaults/main.yml

### Vars
This role uses [tasks/facts.yml] to import and sanitize variables
defined within distribution-specific files within [vars/] to handle
various systems and their derivatives.

[tasks/facts.yml]: https://github.com/inmotionhosting/ansible-role-php_fpm/blob/master/tasks/facts.yml
[vars/]: https://github.com/inmotionhosting/ansible-role-php_fpm/blob/master/vars

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: www
      roles:
         - role: inmotionhosting.php_fpm

License
-------

GPLv3

Author Information
------------------

[InMotion Hosting](https://inmotionhosting.com)
