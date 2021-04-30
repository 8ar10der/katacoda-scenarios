For different use cases, Systemd has designed several different management tools for nspwan containers. We will use the *machinectl* tool, which requires us to create containers in /var/lib/machines/ .

`cd /var/lib/machines/`{{execute}}

Then we will create our first container.

`debootstrap --include=systemd-container --variant=minbase --components=main,universe buster Container1  https://deb.debian.org/debian/`{{execute}}

Here we have used debootstrap to obtain the minimum boot environment required for the buster (debian 10) from Debian and deployed it in the container folder.
> To reduce the container size(<250MB), the parameter `--variant=minbase` is used here to request the most basic file. You can also remove this to get a basic debian environment.

Now if you use the `ls`{{execute}} command, you will find that a folder named Container1 is generated. And this folder is accessible. From the host's view, Systemd-nspawn's containers are just folders by folders. This is because Systemd-nspawn is a lightweight namespace virtualization technology. It completely virtualizes the file system hierarchy, process tree, various IPC subsystems, and hosts and domains.

So that means you can also generate the container wherever you wish and then link it to the /var/lib/machines/ folder using a symbolic link, for example:

`sudo ln -s /home/username/MyContainers/Container1/ /var/lib/machines/`
> Note: Do not use relative paths to create symbolic links, use absolute paths instead.