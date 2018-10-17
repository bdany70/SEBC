### What is ubertask optimization?

Whether to enable ubertask optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

### Where in CM is the Kerberos Security Realm value displayed?

It is diplay in cluster administration settings.

### Which CDH service(s) host a property for enabling Kerberos authentication?

Zookeeper, HDFS, YARN

### How do you upgrade the CM agents?

In my cluster I can use the URL: http://lion1.westeurope.cloudapp.azure.com:7180/cmf/upgrade-wizard/welcome

### Give the `tsquery` statement used to chart Hue's CPU utilization?

select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue

### Name all the roles that make up the Hive service

Gateway, WebHCat Server, Hive Metastore Server, HiveServer2

### What steps must be completed before integrating Cloudera Manager with Kerberos?

Entering in cluster administration and selecting **Enable Kerberos Wizzard** the steps are:

1. Set up a working KDC. Cloudera Manager supports MIT KDC and Active Directory.

2. The KDC should be configured to have non-zero ticket lifetime and renewal lifetime. CDH will not work properly if tickets are not renewable.

3. OpenLdap client libraries should be installed on the Cloudera Manager Server host if you want to use Active Directory. Also, Kerberos client libraries should be installed on ALL hosts.

4. Cloudera Manager needs an account that has permissions to create other accounts in the KDC.
