# Setup Phanbook with Docker(recommend for production)

You can use Docker compose to easily run Phanbook in an isolated environment built with Docker containers. But for now just to use our scripts to do that

## Define the project

Download Phanbook into the current directory:

```
cd /var/www && git clone https://github.com/phanbook/phanbook
```
This will create a directory called phanbook. If you wish, you can rename it to the name of your project.

## Build the project

To build an image from a source repository, create a description file called Dockerfile at the root of your repository. This file will describe the steps to assemble the image.

Then call docker build with the path of your source repository as the argument (for example .). But with something config the above we make it to scripts file phanbook.sh, so you just to running following the command below:

```
chmod +x phanbook ./phanbook docker
```

Which defauts password mysql is ```password__phanbook``` if you want to change password fo mysql just to open ```opsfile/docker/config.env``` file then edit the password you want to used it


Then you go to the url: http://127.0.0.1

If you get something wrong username and password. Just to open ```common/config/config.php``` file and edit it