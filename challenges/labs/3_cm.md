## HDFS list user

```
[hdfs@bdany70-02 ~]$ hdfs dfs -ls /user
Found 6 items
drwxr-xr-x   - fullerton hotels          0 2018-10-19 10:56 /user/fullerton
drwxrwxrwx   - mapred    hadoop          0 2018-10-19 10:41 /user/history
drwxrwxr-t   - hive      hive            0 2018-10-19 10:42 /user/hive
drwxrwxr-x   - hue       hue             0 2018-10-19 10:43 /user/hue
drwxrwxr-x   - oozie     oozie           0 2018-10-19 10:43 /user/oozie
drwxr-xr-x   - raffles   shops           0 2018-10-19 10:56 /user/raffles
```

## http://bdany70-01.westeurope.cloudapp.azure.com:7180/api/v14/hosts

```json
{
  "items" : [ {
    "hostId" : "006ec295-db88-4a74-8922-d68f68259697",
    "ipAddress" : "10.0.1.4",
    "hostname" : "bdany70-01.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://bdany70-01.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/006ec295-db88-4a74-8922-d68f68259697",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16845422592
  }, {
    "hostId" : "e8dbb527-33a3-437b-9d99-ba46b0818621",
    "ipAddress" : "10.0.1.5",
    "hostname" : "bdany70-02.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://bdany70-01.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/e8dbb527-33a3-437b-9d99-ba46b0818621",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16845422592
  }, {
    "hostId" : "c6b21d45-5428-49c5-8d92-85a92a94b119",
    "ipAddress" : "10.0.1.6",
    "hostname" : "bdany70-03.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://bdany70-01.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/c6b21d45-5428-49c5-8d92-85a92a94b119",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16845422592
  }, {
    "hostId" : "e40f03f4-7169-4451-9a99-bbb9c8b74840",
    "ipAddress" : "10.0.1.7",
    "hostname" : "bdany70-04.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://bdany70-01.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/e40f03f4-7169-4451-9a99-bbb9c8b74840",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16845422592
  }, {
    "hostId" : "018d28ad-f5a6-429a-9954-f6e9b2284e01",
    "ipAddress" : "10.0.1.8",
    "hostname" : "bdany70-05.westeurope.cloudapp.azure.com",
    "rackId" : "/default",
    "hostUrl" : "http://bdany70-01.westeurope.cloudapp.azure.com:7180/cmf/hostRedirect/018d28ad-f5a6-429a-9954-f6e9b2284e01",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 16845422592
  } ]
}
```

