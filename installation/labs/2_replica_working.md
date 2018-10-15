[root@lion ~]# wget https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm

--2018-10-15 09:41:26--  https://dev.mysql.com/get/mysql80-community-release-el6-1.noarch.rpm

Risoluzione di dev.mysql.com... 137.254.60.11

Connessione a dev.mysql.com|137.254.60.11|:443... connesso.

HTTP richiesta inviata, in attesa di risposta... 302 Found

Posizione: https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm [segue]

--2018-10-15 09:41:27--  https://repo.mysql.com//mysql80-community-release-el6-1.noarch.rpm

Risoluzione di repo.mysql.com... 23.32.73.150

Connessione a repo.mysql.com|23.32.73.150|:443... connesso.

HTTP richiesta inviata, in attesa di risposta... 200 OK

Lunghezza: 25800 (25K) [application/x-redhat-package-manager]

Salvataggio in: "mysql80-community-release-el6-1.noarch.rpm"

100%[==============================================================================================================================================================>] 25.800      --.-K/s   in 0,08s   

2018-10-15 09:41:27 (307 KB/s) - "mysql80-community-release-el6-1.noarch.rpm" salvato [25800/25800]

[root@lion ~]# rpm -i mysql80-community-release-el6-1.noarch.rpm

avvertimento: mysql80-community-release-el6-1.noarch.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY

[root@lion ~]# yum update

Plugin abilitati:fastestmirror

Impostazione processo di aggiornamento

Loading mirror speeds from cached hostfile

mysql80-community                                                                                                                                                                | 2.5 kB     00:00     

mysql80-community/primary_db                                                                                                                                                     |  27 kB     00:00     

Nessun pacchetto marcato per l'aggiornamento

[root@lion ~]# vi /etc/yum.repos.d/mysql-community.repo 

[root@lion ~]# cat /etc/yum.repos.d/mysql-community.repo 

\# Enable to use MySQL 5.5

[mysql55-community]

name=MySQL 5.5 Community Server

baseurl=http://repo.mysql.com/yum/mysql-5.5-community/el/6/$basearch/

enabled=0

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



\# Enable to use MySQL 5.6

[mysql56-community]

name=MySQL 5.6 Community Server

baseurl=http://repo.mysql.com/yum/mysql-5.6-community/el/6/$basearch/

enabled=0

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



\# Enable to use MySQL 5.7

[mysql57-community]

name=MySQL 5.7 Community Server

baseurl=http://repo.mysql.com/yum/mysql-5.7-community/el/6/$basearch/

enabled=1

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



[mysql80-community]

name=MySQL 8.0 Community Server

baseurl=http://repo.mysql.com/yum/mysql-8.0-community/el/6/$basearch/

enabled=0

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



[mysql-connectors-community]

name=MySQL Connectors Community

baseurl=http://repo.mysql.com/yum/mysql-connectors-community/el/6/$basearch/

enabled=1

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



[mysql-tools-community]

name=MySQL Tools Community

baseurl=http://repo.mysql.com/yum/mysql-tools-community/el/6/$basearch/

enabled=1

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



[mysql-tools-preview]

name=MySQL Tools Preview

baseurl=http://repo.mysql.com/yum/mysql-tools-preview/el/6/$basearch/

enabled=0

gpgcheck=1

gpgkey=file:/etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



[mysql-cluster-7.5-community]

name=MySQL Cluster 7.5 Community

baseurl=http://repo.mysql.com/yum/mysql-cluster-7.5-community/el/6/$basearch/

enabled=0

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql



[mysql-cluster-7.6-community]

name=MySQL Cluster 7.6 Community

baseurl=http://repo.mysql.com/yum/mysql-cluster-7.6-community/el/6/$basearch/

enabled=0

gpgcheck=1

gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

[root@lion ~]# yum install mysql

Plugin abilitati:fastestmirror

Impostazione processo di installazione

Loading mirror speeds from cached hostfile

Il pacchetto mysql è reso obsoleto da mysql-community-client, tentativo di installare mysql-community-client-5.7.23-1.el6.x86_64 al suo posto

Risoluzione dipendenze

--> Esecuzione del controllo di transazione

---> Package mysql-community-client.x86_64 0:5.7.23-1.el6 will be installato

--> Elaborazione dipendenza: mysql-community-libs(x86-64) >= 5.7.9 per il pacchetto: mysql-community-client-5.7.23-1.el6.x86_64

--> Esecuzione del controllo di transazione

---> Package mysql-community-libs.x86_64 0:5.7.23-1.el6 will be installato

--> Elaborazione dipendenza: mysql-community-common(x86-64) >= 5.7.9 per il pacchetto: mysql-community-libs-5.7.23-1.el6.x86_64

--> Esecuzione del controllo di transazione

---> Package mysql-community-common.x86_64 0:5.7.23-1.el6 will be installato

--> Risoluzione delle dipendenze completata



Dipendenze risolte



========================================================================================================================================================================================================

 Pacchetto                                               Arch                                    Versione                                      Repository                                          Dim.

========================================================================================================================================================================================================

Installazione:

 mysql-community-client                                  x86_64                                  5.7.23-1.el6                                  mysql57-community                                   23 M

Installazioni per dipendenze:

 mysql-community-common                                  x86_64                                  5.7.23-1.el6                                  mysql57-community                                  332 k

 mysql-community-libs                                    x86_64                                  5.7.23-1.el6                                  mysql57-community                                  2.1 M



Riepilogo della transazione

========================================================================================================================================================================================================

Installa     3 pacchetti



Dimensione totale del download: 25 M

Dimensione installata: 112 M

Procedere [s/N]: y

Download dei pacchetti:

(1/3): mysql-community-client-5.7.23-1.el6.x86_64.rpm                                                                                                                            |  23 MB     00:00     

(2/3): mysql-community-common-5.7.23-1.el6.x86_64.rpm                                                                                                                            | 332 kB     00:00     

(3/3): mysql-community-libs-5.7.23-1.el6.x86_64.rpm                                                                                                                              | 2.1 MB     00:00     

\--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Totale                                                                                                                                                                   54 MB/s |  25 MB     00:00     

avvertimento: rpmts_HdrFromFdno: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY

Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

Importing GPG key 0x5072E1F5:

 Userid : MySQL Release Engineering <mysql-build@oss.oracle.com>

 Package: mysql80-community-release-el6-1.noarch (installed)

 From   : /etc/pki/rpm-gpg/RPM-GPG-KEY-mysql

Procedere [s/N]: s

Esecuzione rpm_check_debug

Test di transazione in corso

Test di transazione eseguito con successo

Transazione in corso

Attenzione: RPMDB modificato al di fuori di yum.

  Installazione     : mysql-community-common-5.7.23-1.el6.x86_64                                                                                                                                    1/3 

  Installazione     : mysql-community-libs-5.7.23-1.el6.x86_64                                                                                                                                      2/3 

  Installazione     : mysql-community-client-5.7.23-1.el6.x86_64                                                                                                                                    3/3 

  Verifying         : mysql-community-client-5.7.23-1.el6.x86_64                                                                                                                                    1/3 

  Verifying         : mysql-community-libs-5.7.23-1.el6.x86_64                                                                                                                                      2/3 

  Verifying         : mysql-community-common-5.7.23-1.el6.x86_64                                                                                                                                    3/3 



Installato:

  mysql-community-client.x86_64 0:5.7.23-1.el6                                                                                                                                                          



Dipendenza installata:

  mysql-community-common.x86_64 0:5.7.23-1.el6                                                        mysql-community-libs.x86_64 0:5.7.23-1.el6                                                       



Completo!

[root@lion ~]# yum install mysql-server

Plugin abilitati:fastestmirror

Impostazione processo di installazione

Loading mirror speeds from cached hostfile

Il pacchetto mysql-server è reso obsoleto da mysql-community-server, tentativo di installare mysql-community-server-5.7.23-1.el6.x86_64 al suo posto

Risoluzione dipendenze

--> Esecuzione del controllo di transazione

---> Package mysql-community-server.x86_64 0:5.7.23-1.el6 will be installato

--> Elaborazione dipendenza: libnuma.so.1(libnuma_1.2)(64bit) per il pacchetto: mysql-community-server-5.7.23-1.el6.x86_64

--> Elaborazione dipendenza: libnuma.so.1(libnuma_1.1)(64bit) per il pacchetto: mysql-community-server-5.7.23-1.el6.x86_64

--> Elaborazione dipendenza: libnuma.so.1()(64bit) per il pacchetto: mysql-community-server-5.7.23-1.el6.x86_64

--> Esecuzione del controllo di transazione

---> Package numactl.x86_64 0:2.0.9-2.el6 will be installato

--> Risoluzione delle dipendenze completata



Dipendenze risolte



========================================================================================================================================================================================================

 Pacchetto                                               Arch                                    Versione                                      Repository                                          Dim.

========================================================================================================================================================================================================

Installazione:

 mysql-community-server                                  x86_64                                  5.7.23-1.el6                                  mysql57-community                                  153 M

Installazioni per dipendenze:

 numactl                                                 x86_64                                  2.0.9-2.el6                                   base                                                74 k



Riepilogo della transazione

========================================================================================================================================================================================================

Installa     2 pacchetti



Dimensione totale del download: 153 M

Dimensione installata: 775 M

Procedere [s/N]: y

Download dei pacchetti:

(1/2): mysql-community-server-5.7.23-1.el6.x86_64.rpm                                                                                                                            | 153 MB     00:01     

(2/2): numactl-2.0.9-2.el6.x86_64.rpm                                                                                                                                            |  74 kB     00:00     

\--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Totale                                                                                                                                                                   89 MB/s | 153 MB     00:01     

Esecuzione rpm_check_debug

Test di transazione in corso

Test di transazione eseguito con successo

Transazione in corso

  Installazione     : numactl-2.0.9-2.el6.x86_64                                                                                                                                                    1/2 

  Installazione     : mysql-community-server-5.7.23-1.el6.x86_64                                                                                                                                    2/2 

  Verifying         : mysql-community-server-5.7.23-1.el6.x86_64                                                                                                                                    1/2 

  Verifying         : numactl-2.0.9-2.el6.x86_64                                                                                                                                                    2/2 



Installato:

  mysql-community-server.x86_64 0:5.7.23-1.el6                                                                                                                                                          



Dipendenza installata:

  numactl.x86_64 0:2.0.9-2.el6                                                                                                                                                                          



Completo!

[root@tiger ~]# wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz

--2018-10-15 10:16:10--  https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz

Risoluzione di dev.mysql.com... 137.254.60.11

Connessione a dev.mysql.com|137.254.60.11|:443... connesso.

HTTP richiesta inviata, in attesa di risposta... 302 Found

Posizione: https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz [segue]

--2018-10-15 10:16:11--  https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz

Risoluzione di cdn.mysql.com... 23.32.73.150

Connessione a cdn.mysql.com|23.32.73.150|:443... connesso.

HTTP richiesta inviata, in attesa di risposta... 200 OK

Lunghezza: 4434926 (4,2M) [application/x-tar-gz]

Salvataggio in: "mysql-connector-java-5.1.46.tar.gz"



100%[==============================================================================================================================================================>] 4.434.926   3,66M/s   in 1,2s    



2018-10-15 10:16:12 (3,66 MB/s) - "mysql-connector-java-5.1.46.tar.gz" salvato [4434926/4434926]



[root@tiger ~]# tar zxvf mysql-connector-java-5.1.46.tar.gz

mysql-connector-java-5.1.46/

mysql-connector-java-5.1.46/src/

mysql-connector-java-5.1.46/src/com/

mysql-connector-java-5.1.46/src/com/mysql/

mysql-connector-java-5.1.46/src/com/mysql/fabric/

mysql-connector-java-5.1.46/src/com/mysql/fabric/hibernate/

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/exceptions/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/c3p0/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/jboss/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/

mysql-connector-java-5.1.46/src/demo/

mysql-connector-java-5.1.46/src/demo/fabric/

mysql-connector-java-5.1.46/src/demo/fabric/resources/

mysql-connector-java-5.1.46/src/demo/fabric/resources/com/

mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/

mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/fabric/

mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/fabric/demo/

mysql-connector-java-5.1.46/src/doc/

mysql-connector-java-5.1.46/src/doc/sources/

mysql-connector-java-5.1.46/src/lib/

mysql-connector-java-5.1.46/src/org/

mysql-connector-java-5.1.46/src/org/gjt/

mysql-connector-java-5.1.46/src/org/gjt/mm/

mysql-connector-java-5.1.46/src/org/gjt/mm/mysql/

mysql-connector-java-5.1.46/src/testsuite/

mysql-connector-java-5.1.46/src/testsuite/fabric/

mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/

mysql-connector-java-5.1.46/src/testsuite/perf/

mysql-connector-java-5.1.46/src/testsuite/regression/

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/

mysql-connector-java-5.1.46/src/testsuite/simple/

mysql-connector-java-5.1.46/src/testsuite/simple/jdbc4/

mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/

mysql-connector-java-5.1.46/CHANGES

mysql-connector-java-5.1.46/COPYING

mysql-connector-java-5.1.46/README

mysql-connector-java-5.1.46/README.txt

mysql-connector-java-5.1.46/build.xml

mysql-connector-java-5.1.46/mysql-connector-java-5.1.46-bin.jar

mysql-connector-java-5.1.46/mysql-connector-java-5.1.46.jar

mysql-connector-java-5.1.46/src/com/mysql/fabric/FabricCommunicationException.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/FabricConnection.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/FabricStateResponse.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/HashShardMapping.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/RangeShardMapping.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/Response.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/Server.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ServerGroup.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ServerMode.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ServerRole.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardIndex.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardMapping.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardMappingFactory.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardTable.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/ShardingType.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/hibernate/FabricMultiTenantConnectionProvider.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/ErrorReportingExceptionInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLConnectionProperties.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLConnectionProxy.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLDataSource.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/FabricMySQLDriver.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/JDBC4FabricMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/jdbc/JDBC4FabricMySQLConnectionProxy.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/AuthenticatedXmlRpcMethodCaller.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/DigestAuthentication.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/InternalXmlRpcMethodCaller.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/ResultSetParser.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/XmlRpcClient.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/proto/xmlrpc/XmlRpcMethodCaller.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/Client.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Array.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Data.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Fault.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Member.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/MethodCall.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/MethodResponse.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Param.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Params.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/ResponseParser.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Struct.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/base/Value.java

mysql-connector-java-5.1.46/src/com/mysql/fabric/xmlrpc/exceptions/MySQLFabricException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/AbandonedConnectionCleanupThread.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/AssertionFailedException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/AuthenticationPlugin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/BalanceStrategy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/BestResponseTimeBalanceStrategy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Blob.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/BlobFromLocator.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Buffer.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/BufferRow.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ByteArrayRow.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CacheAdapter.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CacheAdapterFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CachedResultSetMetaData.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CallableStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CharsetMapping.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Charsets.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Clob.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CommunicationsException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/CompressedInputStream.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Connection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionFeatureNotAvailableException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionGroup.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionGroupManager.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionImpl.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionLifecycleInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionProperties.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionPropertiesImpl.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ConnectionPropertiesTransform.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Constants.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/DatabaseMetaData.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/DatabaseMetaDataUsingInfoSchema.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/DocsConnectionPropsHelper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Driver.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/EscapeProcessor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/EscapeProcessorResult.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/EscapeTokenizer.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ExceptionInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ExportControlled.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Extension.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/FailoverConnectionProxy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Field.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/IterateBlock.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42CallableStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42Helper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42PreparedStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42ResultSet.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42ServerPreparedStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC42UpdatableResultSet.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4CallableStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ClientInfoProvider.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ClientInfoProviderSP.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4CommentClientInfoProvider.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4Connection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4DatabaseMetaData.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4DatabaseMetaDataUsingInfoSchema.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4LoadBalancedMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4MultiHostMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4MySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4MysqlSQLXML.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4NClob.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4PreparedStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4PreparedStatementHelper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ReplicationMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ResultSet.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4ServerPreparedStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/JDBC4UpdatableResultSet.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LicenseConfiguration.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalanceExceptionChecker.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedAutoCommitInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedConnectionProxy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LoadBalancedMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/LocalizedErrorMessages.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Messages.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MiniAdmin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MultiHostConnectionProxy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MultiHostMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlDataTruncation.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlDefs.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlErrorNumbers.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlIO.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlParameterMetadata.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/MysqlSavepoint.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NamedPipeSocketFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NdbLoadBalanceExceptionChecker.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NetworkResources.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NoSubInterceptorWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NonRegisteringDriver.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NonRegisteringReplicationDriver.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NotImplemented.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/NotUpdatable.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/OperationNotSupportedException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/OutputStreamWatcher.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/PacketTooBigException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ParameterBindings.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/PerConnectionLRUFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/PerVmServerConfigCacheFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/PingTarget.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/PreparedStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ProfilerEventHandlerFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/RandomBalanceStrategy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReflectiveStatementInterceptorAdapter.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnectionGroup.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnectionGroupManager.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationConnectionProxy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationDriver.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ReplicationMySQLConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetImpl.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetInternalMethods.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetMetaData.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ResultSetRow.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowData.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowDataCursor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowDataDynamic.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/RowDataStatic.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/SQLError.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Security.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/SequentialBalanceStrategy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ServerAffinityStrategy.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/ServerPreparedStatement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/SingleByteCharsetConverter.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/SocketFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/SocketMetadata.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/SocksProxySocketFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StandardLoadBalanceExceptionChecker.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StandardSocketFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Statement.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StatementImpl.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StatementInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StatementInterceptorV2.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StreamingNotifiable.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/StringUtils.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/TimeUtil.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/TimeZoneMapping.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/UpdatableResultSet.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Util.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/V1toV2StatementInterceptorAdapter.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/WatchableOutputStream.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/WatchableWriter.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/Wrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/WriterWatcher.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/CachingSha2PasswordPlugin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/MysqlClearPasswordPlugin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/MysqlNativePasswordPlugin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/MysqlOldPasswordPlugin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/authentication/Sha256PasswordPlugin.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/3-0-Compat.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/5-0-Compat.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/clusterBase.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/coldFusion.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/fullDebug.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/maxPerformance.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/configs/solarisMaxPerformance.properties

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/DeadlockTimeoutRollbackMarker.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLDataException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLIntegrityConstraintViolationException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLInvalidAuthorizationSpecException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLNonTransientConnectionException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLNonTransientException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLQueryInterruptedException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLStatementCancelledException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLSyntaxErrorException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTimeoutException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTransactionRollbackException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTransientConnectionException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/MySQLTransientException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/CommunicationsException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLDataException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLIntegrityConstraintViolationException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLInvalidAuthorizationSpecException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLNonTransientConnectionException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLNonTransientException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLQueryInterruptedException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLSyntaxErrorException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTimeoutException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTransactionRollbackException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTransientConnectionException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/exceptions/jdbc4/MySQLTransientException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/c3p0/MysqlConnectionTester.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/jboss/ExtendedMysqlExceptionSorter.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/integration/jboss/MysqlValidConnectionChecker.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/ResultSetScannerInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/ServerStatusDiffInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/interceptors/SessionAssociationInterceptor.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/CallableStatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/ConnectionWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC42CallableStatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC42PreparedStatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4CallableStatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4ConnectionWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4MysqlPooledConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4MysqlXAConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4PreparedStatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4StatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/JDBC4SuspendableXAConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlConnectionPoolDataSource.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlDataSource.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlDataSourceFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlPooledConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXAConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXADataSource.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXAException.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/MysqlXid.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/PreparedStatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/StatementWrapper.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/SuspendableXAConnection.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jdbc2/optional/WrapperBase.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/LoadBalanceConnectionGroupManager.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/LoadBalanceConnectionGroupManagerMBean.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/ReplicationGroupManager.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/jmx/ReplicationGroupManagerMBean.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/Jdk14Logger.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/Log.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/LogFactory.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/LogUtils.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/NullLogger.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/Slf4JLogger.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/log/StandardLogger.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/LoggingProfilerEventHandler.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/ProfilerEvent.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/profiler/ProfilerEventHandler.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/Base64Decoder.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/BaseBugReport.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ErrorMappingsDocGenerator.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/LRUCache.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/PropertiesDocGenerator.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ReadAheadInputStream.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ResultSetUtil.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/ServerController.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/TimezoneDump.java

mysql-connector-java-5.1.46/src/com/mysql/jdbc/util/VersionFSHierarchyMaker.java

mysql-connector-java-5.1.46/src/demo/fabric/Client1_Fabric.java

mysql-connector-java-5.1.46/src/demo/fabric/Employee.java

mysql-connector-java-5.1.46/src/demo/fabric/EmployeesDataSource.java

mysql-connector-java-5.1.46/src/demo/fabric/EmployeesJdbc.java

mysql-connector-java-5.1.46/src/demo/fabric/HibernateFabric.java

mysql-connector-java-5.1.46/src/demo/fabric/resources/com/mysql/fabric/demo/employee.hbm.xml

mysql-connector-java-5.1.46/src/doc/sources/pom.xml

mysql-connector-java-5.1.46/src/lib/c3p0-0.9.1-pre6.jar

mysql-connector-java-5.1.46/src/lib/c3p0-0.9.1-pre6.src.zip

mysql-connector-java-5.1.46/src/lib/jboss-common-jdbc-wrapper-src.jar

mysql-connector-java-5.1.46/src/lib/jboss-common-jdbc-wrapper.jar

mysql-connector-java-5.1.46/src/lib/slf4j-api-1.6.1.jar

mysql-connector-java-5.1.46/src/org/gjt/mm/mysql/Driver.java

mysql-connector-java-5.1.46/src/testsuite/BaseStatementInterceptor.java

mysql-connector-java-5.1.46/src/testsuite/BaseTestCase.java

mysql-connector-java-5.1.46/src/testsuite/UnreliableSocketFactory.java

mysql-connector-java-5.1.46/src/testsuite/fabric/BaseFabricTestCase.java

mysql-connector-java-5.1.46/src/testsuite/fabric/SetupFabricTestsuite.java

mysql-connector-java-5.1.46/src/testsuite/fabric/TestAdminCommands.java

mysql-connector-java-5.1.46/src/testsuite/fabric/TestDumpCommands.java

mysql-connector-java-5.1.46/src/testsuite/fabric/TestResultSetParser.java

mysql-connector-java-5.1.46/src/testsuite/fabric/TestShardMapping.java

mysql-connector-java-5.1.46/src/testsuite/fabric/TestXmlRpcCore.java

mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestBasicConnection.java

mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestFabricMySQLConnectionSharding.java

mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestHABasics.java

mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestHashSharding.java

mysql-connector-java-5.1.46/src/testsuite/fabric/jdbc/TestRegressions.java

mysql-connector-java-5.1.46/src/testsuite/perf/BasePerfTest.java

mysql-connector-java-5.1.46/src/testsuite/perf/LoadStorePerfTest.java

mysql-connector-java-5.1.46/src/testsuite/perf/RetrievalPerfTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/BlobRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/CachedRowsetTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/CallableStatementRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/CharsetRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/ConnectionRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/DataSourceRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/EscapeProcessorRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/MetaDataRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/MicroPerformanceRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/NumbersRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/PooledConnectionRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/ResultSetRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/StatementRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/StressRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/StringRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/SubqueriesRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/SyntaxRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/UtilsRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/ConnectionRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/ExceptionSubclassesTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/MetaDataRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc4/StatementRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/ConnectionRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/ResultSetRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/regression/jdbc42/StatementRegressionTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/BlobTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/CallableStatementTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/CharsetTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/ConnectionTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/DataSourceTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/DateTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/EscapeProcessingTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/MetadataTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/MiniAdminTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/MultiHostConnectionTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/NumbersTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/ReadOnlyCallableStatementTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/ResultSetTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/SSLTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/ServerControllerTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/SimpleTransformer.java

mysql-connector-java-5.1.46/src/testsuite/simple/SplitDBdotNameTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/StatementsTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/StringUtilsTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/TestBug57662Logger.java

mysql-connector-java-5.1.46/src/testsuite/simple/TestLifecycleInterceptor.java

mysql-connector-java-5.1.46/src/testsuite/simple/TransactionTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/TraversalTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/UpdatabilityTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/UtilsTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/XATest.java

mysql-connector-java-5.1.46/src/testsuite/simple/jdbc4/StatementsTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/ConnectionTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/ResultSetTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/jdbc42/StatementsTest.java

mysql-connector-java-5.1.46/src/testsuite/simple/tb2-data.txt.gz

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/ca-cert.pem

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/ca-key.pem

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/ca-truststore

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/certs_howto.txt

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/client-cert.pem

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/client-key.pem

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/client-keystore

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/mykey.pem

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/mykey.pub

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/server-cert.pem

mysql-connector-java-5.1.46/src/testsuite/ssl-test-certs/server-key.pem

[root@tiger ~]# sudo mkdir -p /usr/share/java/

[root@tiger ~]# cd mysql-connector-java-5.1.46

[root@tiger mysql-connector-java-5.1.46]# sudo cp mysql-connector-java-5.1.46-bin.jar /usr/share/java/mysql-connector-java.jar

[root@tiger ~]# mysql -u root -p

Enter password: 

Welcome to the MySQL monitor.  Commands end with ; or \g.

Your MySQL connection id is 12

Server version: 5.7.23-log MySQL Community Server (GPL)



Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.



Oracle is a registered trademark of Oracle Corporation and/or its

affiliates. Other names may be trademarks of their respective

owners.



Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.



mysql> SHOW SLAVE STATUS \G

*************************** 1. row ***************************

​               Slave_IO_State: Waiting for master to send event

​                  Master_Host: lion

​                  Master_User: root

​                  Master_Port: 3306

​                Connect_Retry: 60

​              Master_Log_File: mysql_binary_log.000004

​          Read_Master_Log_Pos: 434

​               Relay_Log_File: tiger-relay-bin.000003

​                Relay_Log_Pos: 661

​        Relay_Master_Log_File: mysql_binary_log.000004

​             Slave_IO_Running: Yes

​            Slave_SQL_Running: Yes

​              Replicate_Do_DB: 

​          Replicate_Ignore_DB: 

​           Replicate_Do_Table: 

​       Replicate_Ignore_Table: 

​      Replicate_Wild_Do_Table: 

  Replicate_Wild_Ignore_Table: 

​                   Last_Errno: 0

​                   Last_Error: 

​                 Skip_Counter: 0

​          Exec_Master_Log_Pos: 434

​              Relay_Log_Space: 1041

​              Until_Condition: None

​               Until_Log_File: 

​                Until_Log_Pos: 0

​           Master_SSL_Allowed: No

​           Master_SSL_CA_File: 

​           Master_SSL_CA_Path: 

​              Master_SSL_Cert: 

​            Master_SSL_Cipher: 

​               Master_SSL_Key: 

​        Seconds_Behind_Master: 0

Master_SSL_Verify_Server_Cert: No

​                Last_IO_Errno: 0

​                Last_IO_Error: 

​               Last_SQL_Errno: 0

​               Last_SQL_Error: 

  Replicate_Ignore_Server_Ids: 

​             Master_Server_Id: 1

​                  Master_UUID: 3f375f3d-d088-11e8-9776-000d3a2dd517

​             Master_Info_File: /var/lib/mysql/master.info

​                    SQL_Delay: 0

​          SQL_Remaining_Delay: NULL

​      Slave_SQL_Running_State: Slave has read all relay log; waiting for more updates

​           Master_Retry_Count: 86400

​                  Master_Bind: 

​      Last_IO_Error_Timestamp: 

​     Last_SQL_Error_Timestamp: 

​               Master_SSL_Crl: 

​           Master_SSL_Crlpath: 

​           Retrieved_Gtid_Set: 

​            Executed_Gtid_Set: 

​                Auto_Position: 0

​         Replicate_Rewrite_DB: 

​                 Channel_Name: 

​           Master_TLS_Version: 

1 row in set (0,00 sec)

