# Setup Phanbook with Docker(recommend for production)

You can use Docker compose to easily run Phanbook in an isolated environment built with Docker containers. But for now just to use our scripts to do that

## Define the project

Download Phanbook into the current directory:

```
cd /var/www && git clone https://github.com/phanbook/docker
```
This will create a directory called phanbook. If you wish, you can rename it to the name of your project.

## Build the project

To build an image from a source repository, create a description file called Dockerfile at the root of your repository. This file will describe the steps to assemble the image.

Then call docker build with the path of your source repository as the argument (for example .). But with something config the above we make it to scripts file phanbook.sh, so you just to running following the command below:

```
cd docker && chmod +x && ./run.sh
```

Which defauts password mysql is ```secret``` if you want to change password fo mysql just to open ```variables.env``` file then edit the password you want to used it

## Get your Droplet’s IP address

You can run the following command to reveal your server’s IP address.

```
ifconfig eth0 | grep inet | awk '{ print $2 }' //45.55.32.209
```

Finish up by visiting your app page (make sure you replace the example ip address with your correct one): http://45.55.32.209. It should look similar to this:

![](/img/docker-demo.png)


If you get something wrong username and password. Just to open ```phanbook/.env``` file and edit it
