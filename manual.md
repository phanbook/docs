These instructions cover installing with MySQL.  You'll need the
Composer package manager (as detailed below) to complete the installation.

### System Requirements

See the [install instructions](install.md) for System Requirements.

### Get the Phanbook code

```
cd /var/www
git clone https://github.com/phanbook/phanbook.git
```

## Installing with Nginx?

If you are using the Nginx web server, you can [download an Nginx
config](https://raw.githubusercontent.com/phanbook/opsfiles/master/templates/nginx/vhost/phanbook.conf).

### Create MySQL database 

Manually import your starter database from the source.sql in phanbook/schema: 

```
cd /var/www/phanbook/schema
mysql -u root -p
mysql> create database mydatabase;
mysql> use mydatabase;
mysql> source source.sql;
```

### Configuration

Copy phanbook/.env.example to phanbook/.env and then edit the values as needed.
You will most likely need to set the following:

```
APP_URL=http://dev.mysite.com

DB_USERNAME=myusername
DB_PASSWORD=mypassword
DB_DATABASE=mydatabase
DB_CHARSET=utf8
DB_HOST=localhost
DB_CONNECTION=mysql
```

If you are not connecting with the root database user, you'll want to grant your
user all privileges on the database:

```
mysql -u root -p
mysql> grant all privileges on mydatabase.* to myusername@localhost identified by
'mypassword';
```

Set permissions for directories and files:

```
cd /var/www/phanbook
chmod 755 -R content
chmod 755 -R public
```

### Installing with Composer

Get Composer...

```
apt-get install composer
```

Once you have Composer installed...

```
cd /var/www/phanbook
composer install --no-ansi --no-dev --no-interaction --no-progress --no-scripts
--optimize-autoloader
```

Done!  You should now have a functional Phanbook site.

### Admin User

After installation, you can log into your site with the admin account:

- Username: admin
- Password: phanbook

As soon as you log in, you'll want to change the admin password to something
unique.
