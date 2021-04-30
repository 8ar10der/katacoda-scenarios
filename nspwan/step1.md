In ubuntu, systemd-nspawn is not ready to use out of the box and we need to install the necessary component.

```bash
apt update
apt install systemd-container -y
```{{execute}}

And we are going to install the debian system environment into the container later, we also need to install the `debootstrap` tool.

```bash
apt install debootstrap debian-archive-keyring -y
```{{execute}}
