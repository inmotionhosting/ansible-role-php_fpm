![Ansible Molecule Pipeline](https://github.com/inmotionhosting/ansible-role-php_fpm/actions/workflows/main.yml/badge.svg) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-php_fpm.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-php_fpm/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-php_fpm.svg)](https://github.com/inmotionhosting/ansible-role-php_fpm/stargazers)

![InMotion Hosting Ultrastack](https://www.inmotionhosting.com/wp-content/uploads/2024/01/ultrastack-logo-black-vertical.png)

# Ansible Role: PHP-FPM

Modular Ansible Role for deploying and configuring PHP-FPM

## Requirements
This Ansible role supports the two latest stable releases of specific
server-focused Linux distributions and aims to follow their deprecation
policies. Additionally we will focus on supporting the latest two stable
releases of each, which at the time of writing are as follows:

* CentOS 7.x
* Debian 11 or later
* Ubuntu 20.04 LTS or later
* AlmaLinux 8.x or later
* RockyLinux 8.x or later

## Dependencies
None.

## Role Variables
Available variables are listed below with their default values (you can also see `defaults/main.yml`)

| Variable | Description |
| -------- | ----------- |
| php_config_ini_path | Default: `/etc/php.ini`
| php_fpm_binary | Default: `php-fpm`. The name of the binary for the php-fpm service
| php_fpm_config_pool_path | Default: `/etc/php-fpm.d`
| php_fpm_daemon | Default: `php-fpm`
| php_request_slowlog_timeout | Default: `0`
| php_fpm_site_errorlog | Default: `/home/{{ system_user }}/logs/{{ site_domain | replace (".", "_") }}.php.error.log`
| php_fpm_slowlog | Default: `/var/log/php-fpm/{{ system_user }}-slow.log`
| php_fpm_socket_path | Default: `/var/run/php-fpm/{{ system_user }}.sock`
| php_packages | The list of PHP packages to install.
| php_version | The PHP version to be used.
| php_version_flat | Default: `{{ php_version \| replace(".", "") }}`

### php.conf
| Variable | Description |
| -------- | ----------- |
| php_conf_session_save_handler | Default: `files`
| php_conf_session_save_path | Default: `/home/{{ system_user }}/session`
| php_conf_soap_wsdl_cache_dir | Default: `/var/lib/php/wsdlcache`

### php.ini
| Variable | Description |
| -------- | ----------- |
| php_ini_allow_url_fopen | Default: `true`
| php_ini_expose_php | Default: `false`
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

## Example Playbook
```yaml
- hosts: www
  roles:
     - role: inmotionhosting.php_fpm
```

## License
GPLv3

## Author Information
[InMotion Hosting](https://inmotionhosting.com)
