# Setup Phanbook with Docker(recommend for production)

You can use Docker compose to easily run Phanbook in an isolated environment built with Docker containers. But for now just to use our scripts to do that

## Define the project

Download Phanbook into the current directory:

```
cd /var/www && git clone https://github.com/phanbook/phanbook
```
This will create a directory called phanbook. If you wish, you can rename it to the name of your project.

## Build the project

To running it just doing following command below:

```
cp env.example .env
docker-compose up -d

```
Then waiting a moment to download on image, but frm api need library php so that you also need running command below

```
docker-compose exec php bash
cd /app/ && composer install

```
Then go to url http://localhost:9090 to import database, to get database
file go to directory [database](./schema), when you finish just open again http://localhost


## Get your Droplet’s IP address

You can run the following command to reveal your server’s IP address.

```
ifconfig eth0 | grep inet | awk '{ print $2 }' //45.55.32.209
```

Finish up by visiting your app page (make sure you replace the example ip address with your correct one): http://45.55.32.209. It should look similar to this:

![](/img/docker-demo.png)


If you get something wrong username and password. Just to open ```phanbook/.env``` file and edit it
