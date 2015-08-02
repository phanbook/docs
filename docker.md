# Quickstart Guide: Setup Phanbook with Docker

You can use Compose to easily run Phanbook in an isolated environment built with Docker containers. But for now just to use our scripts to do that

## Define the project

Download Phanbook into the current directory:

```
git clone https://github.com/phanbook/phanbook
```
This will create a directory called phanbook. If you wish, you can rename it to the name of your project.

## Build the project

To build an image from a source repository, create a description file called Dockerfile at the root of your repository. This file will describe the steps to assemble the image.

Then call docker build with the path of your source repository as the argument (for example .). But with something config the above we make it to scripts file phanbook.sh, so you just to running following the command below:

```
chmod +x phanbook ./phanbook docker
```

Which defauts password mysql is ```password__phanbook``` if you want to change password fo mysql just to running

```
./phanbook.sh docker your_password_mysql

```

Then you go to the url: http://127.0.0.1