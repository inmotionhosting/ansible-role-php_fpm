inmotionhosting.php_fpm
=========

Modular Ansible Role for deploying and configuring PHP-FPM

[![Build Status](https://travis-ci.org/inmotionhosting/ansible-role-php_fpm.png?branch=master)](https://travis-ci.org/inmotionhosting/ansible-role-php_fpm)

Requirements
------------

* CentOS 7.x or later
* Debian 8 or later
* Ubuntu 16.04 LTS or later

Role Variables
--------------

| Variable | Description |
| -------- | ----------- |
| php_config_ini_path | Default: `/etc/php.ini`
| php_config_path | Default: `/etc/php.d`
| php_config_site_path | Default: `{{ php_config_path }}`
| php_fpm_config_path | Default: `/etc/php-fpm.d`
| php_fpm_config_pool_path | Default: `{{ php_fpm_config_path }}`
| php_fpm_daemon | Default: `php-fpm`
| php_fpm_site_errorlog | Default: `/var/log/php-fpm/{{ system_user }}-error.log`
| php_fpm_slowlog | Default: `/var/log/php-fpm/{{ system_user }}-slow.log`
| php_fpm_socket_path | Default: `/var/run/php-fpm/{{ system_user }}.sock`
| php_packages | The list of PHP packages to install.
| php_version | The discovered PHP version.
| php_version_flat | Default: `{{ php_version | replace(".", "") }}`

### php.conf
| Variable | Description |
| -------- | ----------- |
| php_conf_session_save_handler | Default: `files`
| php_conf_session_save_path | Default: `/var/lib/php/session`
| php_conf_soap_wsdl_cache_dir | Default: `/var/lib/php/wsdlcache`

### php.ini
| Variable | Description |
| -------- | ----------- |
| php_ini_allow_url_fopen | Default: `true`
| php_ini_max_execution_time | Default: `60`
| php_ini_max_input_vars | Default: `6200`
| php_ini_memory_limit | Default: `512M`
| php_ini_post_max_size | Default: `128M`
| php_ini_upload_max_filesize | Default: `128M`
| php_ini_user_ini_cache_ttl | Default: `180`
| php_ini_user_ini_filename | Default: `php.ini`
| php_ini_opcache_enable | Default: `true`
| php_ini_opcache_enable_cli | Default: `false`
| php_ini_opcache_force_restart_timeout | Default: `5`
| php_ini_opcache_interned_strings_buffer | Default: `16`
| php_ini_opcache_log_verbosity_level | Default: `0`
| php_ini_opcache_max_accelerated_files | Default: `16536`
| php_ini_opcache_memory_consumption | Default: `512`
| php_ini_opcache_revalidate_freq | Default: `90`
| php_ini_opcache_validate_permission | Default: `true`
| php_ini_opcache_validate_root | Default: `true`
| php_ini_opcache_validate_timestamps | Default: `true`
| php_ini_zlib_output_compression | Default: `false`
| php_ini_zlib_output_compression_level | Default: `9`

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
