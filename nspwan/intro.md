This tutorial will describe how to create multiple isolated containers in Linux and run multiple Jenkins in them using Systemd-nspawn container technology.

If you are want to try on your PC not here or your OS is not Linux. Please read the post in my blog > https://amao.run/en/posts/systemd-nspwan/

And thanks André Brogärd help me to improve this tutorial.

## Background

This section will explain the terms that appear in this tutorial. This will help you to have a better understanding of this tutorial.

### Systemd

Systemd is the name of a set of system components under the Linux operating system, and it provides the functionality to manage systems and services.

### Systemd-nspawn

Systemd-nspawn is a container tool in systemd. It can be used to run commands or operating systems in a lightweight namespace container.

Compared to Docker, Systemd-nspawn can only do process isolation (the feature of the namespace) but not resource isolation. Host-to-container or container-to-container processes do not affect each other. But without restrictions, containers and hosts are sharing the same resources (e.g. CPU processing power). Docker uses cgroups to enforce resource isolation (like namespace, cgroups are a part of the linux kernel).

### Jenkins

An famous open source automation server. With the help of many plugins, Jenkins can help developers automate the building and deploying of software projects.
