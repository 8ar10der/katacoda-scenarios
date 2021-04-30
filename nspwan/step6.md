Now lets create another container.

Do you remember what I said before that a container is a folder? If we want to create similar containers, then we just need to copy the folder and generate a new symbolic link to `/var/lib/machine`. Oh yeah, and don't forget that the new container needs a new configuration file.

Don't forget to close the container before copying it.

1. Turn off container

`machinectl poweroff Container1`{{execute}}

2. Copy container

`cp -r /var/lib/machines/Container1/ /var/lib/machines/Container2/`{{execute}}

3. Copy config file

`cp /etc/systemd/nspawn/Container1.nspawn /etc/systemd/nspawn/Container2.nspawn`{{execute}}

Then check it out

`machinectl list-images`{{execute}}

Then just go into different containers for different configurations according to different needs. For example, change the port number of Jenkins in Container2. After that you can access different ports to control different Jenkins through your browser on host.

To change the port number. You can go to `/etc/default/jenkins` and add --httpPort=8081 or whatever port to JENKINS_ARGS.

Then you should restart Jenkins with `systemctl restart jenkins`.
