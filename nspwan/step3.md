#### 2.4 Setting up the container network

Containers managed by *machinectl* use a private network by default, and the container's network is completely isolated (from the external network as well as from other containers). This would not be suitable for us to manage multiple Jenkins, so we change it to a host networking that allows the host to access the services within the container.

The path to the container configuration file is `/etc/systemd/nspawn/container-name.nspawn`. The name of the configuration file corresponds to the container name.

We edit the configuration file (using nano or vim).

```bash
mkdir /etc/systemd/nspawn/
nano /etc/systemd/nspawn/Container1.nspawn
```{{execute}}

Add the following two lines to the file.

```cfg
[Network]
VirtualEthernet=no
```{{copy}}