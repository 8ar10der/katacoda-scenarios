Now we can use `machinectl` command to manage our containers.

Here I list some basic commands:

```bash
# List all containers
machinectl list-images
# Boot one container
machinectl start <container>
# Shutdown one container
machinectl poweroff <container>
# List running containers
machinectl list
# Login into one container
machinectl login <container>
# Open one shell of container without login.
machinectl shell <container>
```

Firstly, we boot the container.

`machinectl start Container1`{{execute}}

And check is it running:

`machinectl list`{{execute}}

Then we open a shell to change root's password.

`machinectl shell Container1`{{execute}}

`passwd`{{execute}}

And you have to remove this file for login as root

`rm /etc/securetty`{{execute}}

Finally, exit shell.

`exit`{{execute}}

After exiting the container's shell, you can log in to the container with the password

`machinectl login Container1`{{execute}}

> If you forget your password, to terminate the session from inside the container, hold Ctrl and quickly press ] three times. Non-US keyboard users should use % instead of ].
