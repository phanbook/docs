## Introduction
Phanbook is built on the lightning fast PHP framework called Phalcon.
Implemented as a PHP extension, Phalcon offers dramatically better performance
and lower overhead than other PHP frameworks.  Installing Phalcon is easy but
does require that you have root access to your system.

If you already have a development environment that meets all other System
Requirements below, you can [install
Phalcon](https://docs.phalconphp.com/en/latest/reference/install.html)
and then install Phanbook.

### System Requirements

There are a few things that you will need to have set up in order to run
Phanbook:

- A web server: Apache (with mod_rewrite) or Nginx.
- PHP 5.5+ with the following extensions: 
mbstring, pdo_mysql, openssl, json, gd, dom, fileinfo and
[phalcon](https://docs.phalconphp.com/en/latest/reference/install.html). To see
which PHP extensions you have enabled, look at the output of phpinfo().
- Mysql or MariaDB.
- SSH (command-line) access.

### Install Phanbook

There are three ways to install Phanbook:

1. Install via [Vagrant](http://phanbook.com/docs/vagrant).
2. Install via [Docker](http://phanbook.com/docs/docker).
3. [Manually install](http://phanbook.com/docs/manual).
