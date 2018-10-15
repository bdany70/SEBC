MacBook-Pro:SEBC daniele$ ssh training@lion1.westeurope.cloudapp.azure.com

The authenticity of host 'lion1.westeurope.cloudapp.azure.com (104.45.7.249)' can't be established.

RSA key fingerprint is SHA256:+C9Z9+lrdhiQiEq+L2h43ITwLUXFrh5fVtE5Se/hrY4.

Are you sure you want to continue connecting (yes/no)? yes

Warning: Permanently added 'lion1.westeurope.cloudapp.azure.com,104.45.7.249' (RSA) to the list of known hosts.

[training@lion ~]$ cat /etc/redhat-release 

CentOS release 6.8 (Final)

[training@lion ~]$ sudo -i

[root@lion ~]# sysctl vm.swappiness

vm.swappiness = 1

[root@lion ~]# echo 'never' > /sys/kernel/mm/transparent_hugepage/defrag

[root@lion ~]# nano /etc/rc.local 

[root@lion ~]# cat /etc/rc.local 

\#!/bin/sh

\#

\# This script will be executed *after* all the other init scripts.

\# You can put your own initialization stuff in here if you don't

\# want to do the full Sys V style init stuff.



touch /var/lock/subsys/local

for i in `ls /sys/block/sd*/queue/scheduler`

do

echo "noop" > $i

done

echo never > /sys/kernel/mm/transparent_hugepage/enabled

echo never > /sys/kernel/mm/transparent_hugepage/defrag

[root@lion ~]# mount

/dev/sda2 on / type ext4 (rw,discard)

proc on /proc type proc (rw)

sysfs on /sys type sysfs (rw)

devpts on /dev/pts type devpts (rw,gid=5,mode=620)

tmpfs on /dev/shm type tmpfs (rw)

/dev/sda1 on /boot type ext4 (rw,discard)

none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)

/dev/sdb1 on /mnt/resource type ext4 (rw,noatime,discard)

[root@lion ~]# df -h

Filesystem      Size  Used Avail Use% Mounted on

/dev/sda2        49G  803M   46G   2% /

tmpfs           7,9G     0  7,9G   0% /dev/shm

/dev/sda1       240M   45M  183M  20% /boot

/dev/sdb1        99G  2,1G   92G   3% /mnt/resource

[root@lion ~]# ifconfig -a

eth0      Link encap:Ethernet  HWaddr 00:0D:3A:2D:D5:17  

​          inet addr:10.0.0.4  Bcast:10.0.0.255  Mask:255.255.255.0

​          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1

​          RX packets:13864 errors:0 dropped:0 overruns:0 frame:0

​          TX packets:15829 errors:0 dropped:0 overruns:0 carrier:0

​          collisions:0 txqueuelen:1000 

​          RX bytes:6848682 (6.5 MiB)  TX bytes:3042292 (2.9 MiB)



lo        Link encap:Local Loopback  

​          inet addr:127.0.0.1  Mask:255.0.0.0

​          UP LOOPBACK RUNNING  MTU:65536  Metric:1

​          RX packets:0 errors:0 dropped:0 overruns:0 frame:0

​          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0

​          collisions:0 txqueuelen:0 

​          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)



[root@lion ~]# getent ahostsv4 lion

10.0.0.4        STREAM lion.epm5mik4zaauro02j2graiywih.ax.internal.cloudapp.net

10.0.0.4        DGRAM  

10.0.0.4        RAW    

[root@lion ~]# nslookup lion1.westeurope.cloudapp.azure.com

Server:		168.63.129.16

Address:	168.63.129.16#53



Non-authoritative answer:

Name:	lion1.westeurope.cloudapp.azure.com

Address: 104.45.7.249

[root@lion ~]# ps -edaf |grep ntpd

ntp       16001      1  0 08:42 ?        00:00:00 ntpd -u ntp:ntp -p /var/run/ntpd.pid -g

root      16004   1748  0 08:42 pts/0    00:00:00 grep ntpd

[root@lion ~]# ps -edaf |grep nscd

nscd      16076      1  0 08:44 ?        00:00:00 /usr/sbin/nscd

root      16091   1748  0 08:44 pts/0    00:00:00 grep nscd