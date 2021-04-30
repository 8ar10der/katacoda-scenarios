Now we can use `machinectl` command to manage our containers.

Here I list some basic commands:

```bash
# List all containers
machinectl list-images
# Boot one container
machinectl start <container>
# Shutdown one container
machinectl stop <container>
# List running containers
machinectl list
# Login into one container
machinectl login <container>
# Open one shell of container without login.
machinectl shell <container>
```

1. Firstly, we boot the container.

```bash
machinectl start Container1
```{{execute}}

Then we open a shell to change root's password.

```bash
machinectl shell Container1
# When you in the shell
passwd
# Have to remove this file for login as root
rm /etc/securetty
```

2. After exiting the container's shell, you can log in to the container with the password

```bash
sudo machinectl login Container1
```

> 1. If you forget your password, to terminate the session from inside the container, hold Ctrl and quickly press ] three times. Non-US keyboard users should use % instead of ].  
> 2. When you terminate the session in this way, don't forget to re-enter the geine.
