### API Version

```
http://lion1.westeurope.cloudapp.azure.com:7180/api/version
```

```
v19
```

### Cloudera Manager Version

```
http://lion1.westeurope.cloudapp.azure.com:7180/api/v19/cm/version
```

```json
{
  "version" : "5.14.4",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20180707-0439",
  "gitHash" : "0971e84bdceb60db9b96533f46451f40ed8cbdf9",
  "snapshot" : false
}
```

### List users

```
http://lion1.westeurope.cloudapp.azure.com:7180/api/v19/users
```

```json
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "bdany70",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

### Database Server in use

```
http://lion1.westeurope.cloudapp.azure.com:7180/api/v19/cm/scmDbInfo
```

```json
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```

