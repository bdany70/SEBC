# Show tables

```
[bdany70@elephant ~]$ klist -l
Principal name                 Cache name
--------------                 ----------
[bdany70@elephant ~]$ kinit bdany70@HADOOP.COM
Password for bdany70@HADOOP.COM: 
[bdany70@elephant ~]$ klist -l
Principal name                 Cache name
--------------                 ----------
bdany70@HADOOP.COM             FILE:/tmp/krb5cc_501
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
scan complete in 1ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017144141_e736d410-dcd0-4117-aa30-f6f92d3526a1): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017144141_e736d410-dcd0-4117-aa30-f6f92d3526a1); Time taken: 1.212 seconds
INFO  : Executing command(queryId=hive_20181017144141_e736d410-dcd0-4117-aa30-f6f92d3526a1): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017144141_e736d410-dcd0-4117-aa30-f6f92d3526a1); Time taken: 0.587 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (3.405 seconds)
0: jdbc:hive2://localhost:10000/default> create role sentry_admin;
INFO  : Compiling command(queryId=hive_20181017144242_1c2f8097-018d-4b20-a356-ac1ed4f174b3): create role sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017144242_1c2f8097-018d-4b20-a356-ac1ed4f174b3); Time taken: 0.119 seconds
INFO  : Executing command(queryId=hive_20181017144242_1c2f8097-018d-4b20-a356-ac1ed4f174b3): create role sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017144242_1c2f8097-018d-4b20-a356-ac1ed4f174b3); Time taken: 0.482 seconds
INFO  : OK
No rows affected (0.617 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20181017144242_da9dc324-ce87-468b-b26b-8d6377f95f40): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017144242_da9dc324-ce87-468b-b26b-8d6377f95f40); Time taken: 0.101 seconds
INFO  : Executing command(queryId=hive_20181017144242_da9dc324-ce87-468b-b26b-8d6377f95f40): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017144242_da9dc324-ce87-468b-b26b-8d6377f95f40); Time taken: 0.157 seconds
INFO  : OK
No rows affected (0.274 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP bdany70;
INFO  : Compiling command(queryId=hive_20181017144343_aa3093d0-8434-4116-ab5d-c0c864aa498b): GRANT ROLE sentry_admin TO GROUP bdany70
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017144343_aa3093d0-8434-4116-ab5d-c0c864aa498b); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20181017144343_aa3093d0-8434-4116-ab5d-c0c864aa498b): GRANT ROLE sentry_admin TO GROUP bdany70
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017144343_aa3093d0-8434-4116-ab5d-c0c864aa498b); Time taken: 0.037 seconds
INFO  : OK
No rows affected (0.183 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017144343_3137c319-6472-4f1a-865e-ab6a9197130c): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017144343_3137c319-6472-4f1a-865e-ab6a9197130c); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20181017144343_3137c319-6472-4f1a-865e-ab6a9197130c): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017144343_3137c319-6472-4f1a-865e-ab6a9197130c); Time taken: 0.303 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.465 seconds)
```

# Show tables as George and Ferdinand

```
[bdany70@elephant ~]$ kinit george@HADOOP.COM
Password for george@HADOOP.COM: 
[bdany70@elephant ~]$ beeline 
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> show tables;
No current connection
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017145757_228acadc-7e62-4c8a-b938-651e213bf476): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017145757_228acadc-7e62-4c8a-b938-651e213bf476); Time taken: 0.091 seconds
INFO  : Executing command(queryId=hive_20181017145757_228acadc-7e62-4c8a-b938-651e213bf476): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017145757_228acadc-7e62-4c8a-b938-651e213bf476); Time taken: 0.27 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.478 seconds)
0: jdbc:hive2://localhost:10000/default> Closing: 0: jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
[bdany70@elephant ~]$ kinit ferdinand@HADOOP.COM
Password for ferdinand@HADOOP.COM: 
[bdany70@elephant ~]$ beeline 
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.13.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
scan complete in 4ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/elephant1.westeurope.cloudapp.azure.com@HADOOP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.3)
Driver: Hive JDBC (version 1.1.0-cdh5.13.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20181017145858_dc316c5a-4477-47f4-9b6c-d6d9af41447a): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017145858_dc316c5a-4477-47f4-9b6c-d6d9af41447a); Time taken: 0.085 seconds
INFO  : Executing command(queryId=hive_20181017145858_dc316c5a-4477-47f4-9b6c-d6d9af41447a): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017145858_dc316c5a-4477-47f4-9b6c-d6d9af41447a); Time taken: 0.289 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.493 seconds)
```

