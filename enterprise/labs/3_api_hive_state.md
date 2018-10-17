### Stop Hive

```shell
curl -X POST -u bdany70:cloudera 'http://lion1.westeurope.cloudapp.azure.com:7180/api/v1/clusters/bdany70/services/hive/commands/stop'
```

```json
{
  "id" : 545,
  "name" : "Stop",
  "startTime" : "2018-10-17T08:56:48.432Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```shell
curl -u bdany70:cloudera 'http://lion1.westeurope.cloudapp.azure.com:7180/api/v1/commands/545'
```

```json
{
  "id" : 545,
  "name" : "Stop",
  "startTime" : "2018-10-17T08:56:48.432Z",
  "endTime" : "2018-10-17T08:56:50.140Z",
  "active" : false,
  "success" : true,
  "resultMessage" : "Successfully stopped service.",
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  },
  "children" : {
    "items" : [ {
      "id" : 546,
      "name" : "Stop",
      "startTime" : "2018-10-17T08:56:48.440Z",
      "endTime" : "2018-10-17T08:56:50.140Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVESERVER2-c2c9702b948bd69c47d98870badccdb7"
      }
    }, {
      "id" : 547,
      "name" : "Stop",
      "startTime" : "2018-10-17T08:56:48.442Z",
      "endTime" : "2018-10-17T08:56:50.134Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully stopped process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVEMETASTORE-c2c9702b948bd69c47d98870badccdb7"
      }
    } ]
  }
}
```

### Start Hive

```shell
curl -X POST -u bdany70:cloudera 'http://lion1.westeurope.cloudapp.azure.com:7180/api/v1/clusters/bdany70/services/hive/commands/start'
```

```json
{
  "id" : 549,
  "name" : "Start",
  "startTime" : "2018-10-17T08:57:50.856Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```shell
curl u bdany70:cloudera 'http://lion1.westeurope.cloudapp.azure.com:7180/api/v1/commands/549'
```

```json
{
  "id" : 549,
  "name" : "Start",
  "startTime" : "2018-10-17T08:57:50.856Z",
  "endTime" : "2018-10-17T08:58:13.457Z",
  "active" : false,
  "success" : true,
  "resultMessage" : "Successfully started service.",
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  },
  "children" : {
    "items" : [ {
      "id" : 551,
      "name" : "Start",
      "startTime" : "2018-10-17T08:57:50.927Z",
      "endTime" : "2018-10-17T08:58:13.453Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully started process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVEMETASTORE-c2c9702b948bd69c47d98870badccdb7"
      }
    }, {
      "id" : 550,
      "name" : "Start",
      "startTime" : "2018-10-17T08:57:50.878Z",
      "endTime" : "2018-10-17T08:58:13.448Z",
      "active" : false,
      "success" : true,
      "resultMessage" : "Successfully started process.",
      "serviceRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive"
      },
      "roleRef" : {
        "clusterName" : "cluster",
        "serviceName" : "hive",
        "roleName" : "hive-HIVESERVER2-c2c9702b948bd69c47d98870badccdb7"
      }
    } ]
  }
}
```

### Check Hive

```shell
curl -u bdany70:cloudera http://lion1.westeurope.cloudapp.azure.com:7180/api/v1/clusters/bdany70/services/hive
```

```json
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://10.0.0.4:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false
}
```

