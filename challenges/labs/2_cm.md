# Install Cloudera Manager

## /etc/yum.repos.d

```
[root@bdany70-01 ~]# ls -l /etc/yum.repos.d/
totale 48
-rw-r--r-- 1 root root 1533 20 set  2016 CentOS-Base.repo
-rw-r--r-- 1 root root  647 26 giu 16:52 CentOS-Debuginfo.repo
-rw-r--r-- 1 root root  289 26 giu 16:52 CentOS-fasttrack.repo
-rw-r--r-- 1 root root  630 26 giu 16:52 CentOS-Media.repo
-rw-r--r-- 1 root root 8854 26 giu 16:52 CentOS-Vault.repo
-rw-r--r-- 1 root root  213 19 ott 10:08 cloudera-manager.repo
-rw-r--r-- 1 root root  210 19 ott 09:50 cloudera-manager.repo.~1~
-rw-r--r-- 1 root root 1862 22 feb  2018 mysql-community.repo
-rw-r--r-- 1 root root 1885 22 feb  2018 mysql-community-source.repo
-rw-r--r-- 1 root root  282 20 set  2016 OpenLogic.repo
```

## scm_prepare_database.sh

```
/usr/share/cmf/schema/scm_prepare_database.sh -h bdany70-02.westeurope.cloudapp.azure.com mysql scm scm Scm.1977
```

