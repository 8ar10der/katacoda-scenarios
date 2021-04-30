Now we are in the Containers, let's install the Jenkins.

1. Install necessary packages.
```bash
apt update
apt install wget nano gnupg
```{{execute}}

2. Install Jenkins

```bash
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | apt-key add -
sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
apt update
apt install jenkins
```{{execute}}

3. Start Jenkins

`systemctl start jenkins`{{execute}}

4. Now you can open Jenkins page in browser at host:

Default port 8080: https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/
