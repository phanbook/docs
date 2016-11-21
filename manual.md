### Requirements
- PHP 5.4+
- Phalcon 2.0.x
- Nginx or Apache
- MariaDB or Mysql

You can see how to install LEMP stack [here](https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-12-04) and [Phalcon](https://docs.phalconphp.com/en/latest/reference/install.html)

when you have requirements just to clone it from github

```
cd /usr/share/nginx/html
git clone https://github.com/phanbook/phanbook.git
```

## Configuring Nginx for Phanbook

Go to this [url](https://raw.githubusercontent.com/phanbook/opsfiles/master/templates/nginx/vhost/phanbook.conf) to download nginx config, after that adding file following content(/etc/nginx/nginx.conf)


### Create MySQL database 

You need to create database with name phanbook or anything name. Import the file schema/phanbook.sql into database

```
mysql -u root -p schema < schema/phanbook.sql
```

### Config

You need to copy file .env.example to .env in directory then edit params of database connection some like 

```
APP_URL=http://phanbook.dev

DB_USERNAME=phanbook
DB_PASSWORD=secret
DB_DATABASE=phanbook
DB_CHARSET=utf8
DB_HOST=localhost
DB_CONNECTION=mysql

```
Set permissions for directories and files:

```
chmod 777 -R content
chmod 777 -R public
```
### Installing vendor

Because we have user some library PHP , so we need to install to Phanbook can working, just to add following command below

```
composer install --no-ansi --no-dev --no-interaction --no-progress --no-scripts --optimize-autoloader
```
### Username 

Default we have setup a user with

- Username: admin
- Password: phanbook

You should change password now
