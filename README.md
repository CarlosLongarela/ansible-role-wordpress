Ansible Role: WordPress
=========

[![Build Status](https://travis-ci.org/CarlosLongarela/ansible-role-wordpress.svg?branch=master)](https://travis-ci.org/CarlosLongarela/ansible-role-wordpress)
[![Percentage of issues still open](http://isitmaintained.com/badge/open/CarlosLongarela/ansible-role-wordpress.svg)](http://isitmaintained.com/project/CarlosLongarela/ansible-role-wordpress "Percentage of issues still open")
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/CarlosLongarela/ansible-role-wordpress.svg)](http://isitmaintained.com/project/CarlosLongarela/ansible-role-wordpress "Average time to resolve an issue")

WordPress site configuration and installation with WP Cli that also is installed.

Requirements
------------

None.

Role Variables
--------------

    wp_cli_url: "https://raw.github.com/wp-cli/builds/gh-pages/phar/wp-cli.phar"
    wp_cli_bin: "wp"
    wp_cli_path: "/usr/bin/{{ wp_cli_bin}}"
    wp_cli_packages: []

    wp_cli_wp_locale: "es_ES"
    wp_cli_wp_path: "/home/webs/wordpress"
    wp_cli_wp_version: "latest"

    wp_cli_wp_db: "dbname"
    wp_cli_wp_db_user: "dbuser"
    wp_cli_wp_db_pass: "dbpassword"
    wp_cli_wp_db_host: "localhost"
    wp_cli_wp_dp_prefix: "wp_"

    wp_cli_wp_url: "example.com"
    wp_cli_wp_title: "WordPress Site"
    wp_cli_wp_admin_user: "supervisor"
    wp_cli_wp_admin_password: "strongpassword"
    wp_cli_wp_admin_email: "info@example.com"

Dependencies
------------

- [CarlosLongarela.mariadb](https://galaxy.ansible.com/CarlosLongarela/mariadb/)
- [CarlosLongarela.nginx](https://galaxy.ansible.com/CarlosLongarela/nginx/)
- [CarlosLongarela.php7](https://galaxy.ansible.com/CarlosLongarela/php7/)

Example Playbook
----------------

    - hosts: servers

      gather_facts: no
      become: true

      vars:
        wp_cli_wp_locale: "es_ES"
        wp_cli_wp_path: "/home/webs/mywordpress"

        wp_cli_wp_db: "mydbname"
        wp_cli_wp_db_user: "mydbuser"
        wp_cli_wp_db_pass: "mydbpassword"
        wp_cli_wp_db_host: "localhost"
        wp_cli_wp_dp_prefix: "mywp_"

        wp_cli_wp_url: "https://example.com"
        wp_cli_wp_title: "My WordPress Site"
        wp_cli_wp_admin_user: "mysuser"
        wp_cli_wp_admin_password: "mypassword"
        wp_cli_wp_admin_email: "myinfo@example.com"

      roles:
         - { role: CarlosLongarela.wordpress }

License
-------

GPLv2

Author Information
------------------

This role was created in 2017, May by [Carlos Longarela](mailto:carlos@longarela.eu), from [Taberna WordPress](https://tabernawp.com/).
