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

Adding file following config nginx(/etc/nginx/nginx.conf) for Ubuntu

```
server {
    listen   80;
    server_name localhost;

    index index.php index.html index.htm;
    set  $root_path '/usr/share/nginx/html/phanbook/public';
    root $root_path;
    try_files $uri $uri/ @rewrite;

    location @rewrite {
        rewrite ^/(.*)$ /index.php?_url=/$1;
    }
    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass   unix:/var/run/php5-fpm.sock;
        fastcgi_index  index.php;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~* ^/(css|img|js|flv|swf|download)/(.+)$ {
        root $root_path;
    }

    location ~ /\.ht {
        deny all;
    }
}
```
### Create MySQL database 

You need to create database with name phanbook or anything name. Import the file schema/phanbook.sql into database

```
mysql -u root -p schema < schema/phanbook.sql
```

### Config

You need to copy file .env.example to .env in directory then edit params of database connection some like 

```
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
