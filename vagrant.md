# Phanbook Developer Install Guide (Vagrant)


The following instructions will automatically download and provision a virtual machine for you to begin hacking
on Phanbook with:

### Getting Started

1. Install Git: http://git-scm.com/downloads (or [GitHub for Windows](http://windows.github.com/) if you want a GUI). Recommend use github for Windows
2. Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
3. Install Vagrant: http://www.vagrantup.com/ (We require Vagrant 1.7.2 or later)
4. Open a terminal
5. Clone the project: `git clone https://github.com/Phanbook/phanbook.git`
6. Enter the project directory: `cd Phanbook` (Recommendation Create your workspace directory and clone project there. C:/workspace/phanbook/)

### Using Vagrant

When you're ready to start working, boot the VM:

```
chmod +x phanbook.sh && ./phanbook.sh up
```
Or you can runninng via command below

```
cd opsfile && vagrant up
```

Vagrant will prompt you for your admin password. This is so it can mount your local files inside the VM for an easy workflow.

(The first time you do this, it will take a while as it downloads the VM image and installs it. Go grab a coffee.)

**Note to Linux users**: Your Phanbook directory cannot be on an ecryptfs mount or you will receive an error: `exportfs: /home/your/path/to/Phanbook does not support NFS export`

**Note to OSX/Linux users**: Vagrant will mount your local files via an NFS share. Therefore, make sure that NFS is installed or else you'll receive the error message:

```
Mounting NFS shared folders failed. This is most often caused by the NFS
client software not being installed on the guest machine. Please verify
that the NFS client software is properly installed, and consult any resources
specific to the linux distro you're using for more information on how to
do this.
```

For example, on Ubuntu, you can install NFS support by installing nfs-kernel-server with `apt-get install`.

Once the machine has booted up, you can shell into it by typing:

```
./phanbook.sh ssh
```

The Phanbook code is found in the /vagrant directory in the image.

**Note to Windows users**: You cannot run ```vagrant ssh``` from a cmd prompt; you'll receive the error message:

```
`vagrant ssh` isn't available on the Windows platform. You are still able
to SSH into the virtual machine if you get a Windows SSH client (such as
PuTTY). The authentication information is shown below:

Host: 127.0.0.1
Port: 2222
Username: vagrant
Private key: C:/Users/Your Name/.vagrant.d/insecure_private_key
```

At this point, you will want to get an SSH client, and use it to connect to your Vagrant VM instead. We recommend
PuTTY:

**[PuTTY Download Link](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)**

You may use this client to connect to the VM by using ```vagrant/vagrant``` as your username/password, or by [using
PuTTYGen to import the insecure_private_key file](http://jason.sharonandjason.com/key_based_putty_logins_mini_how_to.htm)
(mentioned above) into a PuTTY profile to quickly access your VM.

### Let's contribution for phanbook.
1. checkout your new branch (feature/your-name-branch)

```
$ ## creating new branch
$ git checkout -b feature/{your-new-branch-name}
```
2. commit your files and let's push

```
git push origin feature/{your-new-branch-name}
```

### Shutting down the VM

When you're done working on Phanbook, you can shut down Vagrant with:

```
cd opsfiles && vagrant halt
```

or you can running 

```
./phanbook.sh halt
```
