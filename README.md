Ubuntu LTS with SSH (Docker)
=========

A Docker file to build a [docker.io] base container with Ubuntu LTS and a sshd service.
[docker.io]: http://docker.io
Nice and easy way to get any server up and running using docker.


Instructions
-----------
 - Install Docker. Read http://docs.docker.io/en/latest/installation/ for instructions
 - Pull the repository
   `git clone https://github.com/art567/docker-ubuntu-sshd.git`
 - Build the container
   `sudo docker build -t art567/ubuntu .`
 - Run the container
   `sudo docker run -d=true -p=2222:22 -v=/opt/data:/data art567/ubuntu /start`
 - Your container will start and bind ssh to 2222 port.
 - Find IP Address using `ifconfig`
 - Connect to the SSH server
   `ssh root@<ip-address> -p 2222`
 - If you don't want to deal with root:
   `ssh master@<ip-address> -p 2222`

**IMPORTANT:**

   Please modify your passwords in Dockerfile before building image!


Versions
-----------
Some branches represents Ubuntu versions.

Branch `master` is always represented by latest Ubuntu LTS

   For example:
   - 12.04 - Ubuntu 12.04.5 LTS
   - 14.04 - Ubuntu 14.04.3 LTS

