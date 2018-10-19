# VMs

I use 5 Azure machines with 4 vcores and 16 GB of RAM. Every machine has 3 disks one for the OS, one temporary and one for the datas.

The machines are:

- bdany70-01.westeurope.cloudapp.azure.com
- bdany70-02.westeurope.cloudapp.azure.com
- bdany70-03.westeurope.cloudapp.azure.com
- bdany70-04.westeurope.cloudapp.azure.com
- bdany70-05.westeurope.cloudapp.azure.com

## Linux Version

```
[training@bdany70-02 ~]$ cat /etc/redhat-release 
CentOS release 6.10 (Final)
[training@bdany70-02 ~]$ 
```

## Disks

```
[training@bdany70-02 ~]$ mount
/dev/sda2 on / type ext4 (rw,discard)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw)
/dev/sda1 on /boot type ext4 (rw,discard)
/dev/sdc1 on /data/1 type ext4 (rw,noatime)
/dev/sdc2 on /data/2 type ext4 (rw,noatime)
/dev/sdc3 on /data/3 type ext4 (rw,noatime)
/dev/sdc5 on /data/4 type ext4 (rw,noatime)
/dev/sdc6 on /data/5 type ext4 (rw,noatime)
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
/dev/sdb1 on /mnt/resource type ext4 (rw,noatime,discard)
[training@bdany70-02 ~]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2        49G  1,6G   45G   4% /
tmpfs           7,8G     0  7,8G   0% /dev/shm
/dev/sda1       240M   70M  159M  31% /boot
/dev/sdc1        50G   52M   49G   1% /data/1
/dev/sdc2        50G   52M   49G   1% /data/2
/dev/sdc3        50G   52M   49G   1% /data/3
/dev/sdc5        50G   52M   49G   1% /data/4
/dev/sdc6        50G   52M   49G   1% /data/5
/dev/sdb1        99G  2,1G   92G   3% /mnt/resource
```

## Repolis

This is repolist before Cloudera configuration:

```
[root@bdany70-02 ~]# yum repolist enabled
Plugin abilitati:fastestmirror
Loading mirror speeds from cached hostfile
base                                                                                                                                                                             | 3.7 kB     00:00     
extras                                                                                                                                                                           | 3.4 kB     00:00     
mysql-connectors-community                                                                                                                                                       | 2.5 kB     00:00     
mysql-connectors-community/primary_db                                                                                                                                            |  24 kB     00:00     
mysql-tools-community                                                                                                                                                            | 2.5 kB     00:00     
mysql-tools-community/primary_db                                                                                                                                                 |  43 kB     00:00     
mysql80-community                                                                                                                                                                | 2.5 kB     00:00     
mysql80-community/primary_db                                                                                                                                                     |  27 kB     00:00     
openlogic                                                                                                                                                                        | 2.9 kB     00:00     
updates                                                                                                                                                                          | 3.4 kB     00:00     
id repo                                                                                   nome repo                                                                                                stato
base                                                                                      CentOS-6 - Base                                                                                          6713
extras                                                                                    CentOS-6 - Extras                                                                                          33
mysql-connectors-community                                                                MySQL Connectors Community                                                                                 59
mysql-tools-community                                                                     MySQL Tools Community                                                                                      65
mysql80-community                                                                         MySQL 8.0 Community Server                                                                                 29
openlogic                                                                                 CentOS-6 - openlogic packages for x86_64                                                                  104
updates                                                                                   CentOS-6 - Updates                                                                                        205
repolist: 7208
```

## /etc/passwd

```
[root@bdany70-02 ~]# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
uucp:x:10:14:uucp:/var/spool/uucp:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
games:x:12:100:games:/usr/games:/sbin/nologin
gopher:x:13:30:gopher:/var/gopher:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
vcsa:x:69:69:virtual console memory owner:/dev:/sbin/nologin
saslauth:x:499:76:Saslauthd user:/var/empty/saslauth:/sbin/nologin
postfix:x:89:89::/var/spool/postfix:/sbin/nologin
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
training:x:500:500::/home/training:/bin/bash
ntp:x:38:38::/etc/ntp:/sbin/nologin
nscd:x:28:28:NSCD Daemon:/:/sbin/nologin
raffles:x:2000:502::/home/raffles:/bin/bash
fullerton:x:3000:501::/home/fullerton:/bin/bash
```

## /etc/group

```
root@bdany70-02 ~]# cat /etc/group
root:x:0:
bin:x:1:bin,daemon
daemon:x:2:bin,daemon
sys:x:3:bin,adm
adm:x:4:adm,daemon
tty:x:5:
disk:x:6:
lp:x:7:daemon
mem:x:8:
kmem:x:9:
wheel:x:10:
mail:x:12:mail,postfix
uucp:x:14:
man:x:15:
games:x:20:
gopher:x:30:
video:x:39:
dip:x:40:
ftp:x:50:
lock:x:54:
audio:x:63:
nobody:x:99:
users:x:100:
floppy:x:19:
vcsa:x:69:
utmp:x:22:
utempter:x:35:
cdrom:x:11:
tape:x:33:
dialout:x:18:
saslauth:x:76:
postdrop:x:90:
postfix:x:89:
fuse:x:499:
sshd:x:74:
training:x:500:
ntp:x:38:
nscd:x:28:
hotels:x:501:
shops:x:502:
```

