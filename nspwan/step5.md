Now we are in the Containers, let's install the Jenkins.

1. Install necessary packages.
```bash
apt update
apt install -y wget nano sl gnupg openjdk-11-jre
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

4. Config your jenkins

Now you can open Jenkins page in browser at host via port 8080:

https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/
