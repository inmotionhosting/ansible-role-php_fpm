inmotionhosting.php_fpm
=========

Modular Ansible Role for deploying and configuring PHP-FPM

[![Build Status](https://travis-ci.org/inmotionhosting/php_fpm.png?branch=master)](https://travis-ci.org/inmotionhosting/php_fpm)

Requirements
------------

* CentOS 7.x or later
* Debian 9 or later
* Ubuntu 16.04 LTS or later

Role Variables
--------------

### Defaults
| Variable | Description |
| -------- | ----------- |
| php_fpm_daemon | The name of the PHP-FPM daemon.

### Vars
| Variable | Description |
| -------- | ----------- |
| php_conf_dir | The top-level PHP configuration directory name.
| php_fpm_config_dir | The PHP-FPM configuration directory.
| php_packages | The packages to install for PHP.
| php_version | The target PHP version.
| php_version_flat | The flattened PHP version.<br><br>Example: `73`


Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: inmotionhosting.php_fpm

License
-------

GPLv3

Author Information
------------------

InMotion Hosting
