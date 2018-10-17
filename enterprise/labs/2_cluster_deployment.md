```json
{
  "timestamp" : "2018-10-17T08:46:58.165Z",
  "clusters" : [ {
    "name" : "bdany70",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "691011584"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5rtab233piqyirbfewnxlu4oy"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "lion"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "691011584"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3m9u80e847a699qy257vzzwzj"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "lion"
        }, {
          "name" : "database_password",
          "value" : "hue"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-c2c9702b948bd69c47d98870badccdb7"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bu21e1s8fq821eqzgjf70nf6a"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "9df11c7a-9da0-4a0c-bfd6-992fcf93957a"
          }, {
            "name" : "role_jceks_password",
            "value" : "8q0cgnl47wr8p20ogq026gijv"
          }, {
            "name" : "secret_key",
            "value" : "jNhg5THDUtXEojNnAdLj1n5WTN5aad"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "691011584"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/data/1/dfs/dn,/data/2/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "10555310080"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/1/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/data/1/dfs/nn,/data/2/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "691011584"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/data/1/dfs/snn,/data/2/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "691011584"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_client_use_datanode_hostname",
          "value" : "true"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "VhJPZWf88YLccWjNos3UqPU9DN2P34"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "Bb70wo5I7ZYqDY9rSjsRAehPqO19mY"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "2xQoTDvpULm8g1qIZEQyS321QGKCT5"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-34ef6817bc7dce517d75c76fea2db1e7",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "48a01078-dfc2-4b57-8b3d-d07b7cd12c9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3wg9h40vu0yn89d25sdmr5uxp"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-6a094bc6eaba971db536a7059f0ed9ff",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "00f946f8-97ca-47e9-8f7f-d5be1482c350"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1a4xwk5wo9ngo5r5ccu061939"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-ab162b5e9d62f403d980181297543801",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "4305ebd2-6685-451e-9443-fe865f1206a4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "12hb5vu0qk54n6i2wd9lbsjpz"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-bfeed17396f5731448367e68127a3f11",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "5b2e7ee2-a73e-4c21-ae48-2faf43afc655"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4pncx0edvahkw7dj4kc8ziwed"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-ab162b5e9d62f403d980181297543801",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "4305ebd2-6685-451e-9443-fe865f1206a4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b507aodt2haj5nuviztk83dra"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "577qm06rjssfcmsfxv0w6zu0i"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-c2c9702b948bd69c47d98870badccdb7",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7llqpugutyhbqimsayvteaz7r"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-34ef6817bc7dce517d75c76fea2db1e7",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "48a01078-dfc2-4b57-8b3d-d07b7cd12c9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a94oekysljres1kck69vdj1wo"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-6a094bc6eaba971db536a7059f0ed9ff",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "00f946f8-97ca-47e9-8f7f-d5be1482c350"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7c7mwlcw9zcn7msyr0soh3phm"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-bfeed17396f5731448367e68127a3f11",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "5b2e7ee2-a73e-4c21-ae48-2faf43afc655"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dhfond5z5k8pnoj6ml5o3ulwe"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-ab162b5e9d62f403d980181297543801",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "4305ebd2-6685-451e-9443-fe865f1206a4"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "59"
          }, {
            "name" : "role_jceks_password",
            "value" : "7mn60drb6reavdds3oqfj92z"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-c2c9702b948bd69c47d98870badccdb7",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "44"
          }, {
            "name" : "role_jceks_password",
            "value" : "ct54jyjf1vfd6r0rkes1dcy9n"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "JOBHISTORY",
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "691011584"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/data/1/yarn/nm,/data/2/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/mnt/resource/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "5428"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "691011584"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5428"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "lnTeYJpytAqvq5VHQsz4vbCfBXKCUe"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-c2c9702b948bd69c47d98870badccdb7",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bvgmopormj2i5d4txjfmh1hbb"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-34ef6817bc7dce517d75c76fea2db1e7",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "48a01078-dfc2-4b57-8b3d-d07b7cd12c9a"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9vlq1flejikq9qgfbzjaxcnok"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-6a094bc6eaba971db536a7059f0ed9ff",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "00f946f8-97ca-47e9-8f7f-d5be1482c350"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3jqwbdj8elu2i5qagpcojef5n"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-ab162b5e9d62f403d980181297543801",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "4305ebd2-6685-451e-9443-fe865f1206a4"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5w0hrehwgkdmfsmvw6l46s36g"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-bfeed17396f5731448367e68127a3f11",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "5b2e7ee2-a73e-4c21-ae48-2faf43afc655"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5wfl2sjvwe5uz0qibo2e8vf3m"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-c2c9702b948bd69c47d98870badccdb7",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "51"
          }, {
            "name" : "role_jceks_password",
            "value" : "2of5dqeihx4kggnfzkiozarjn"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "691011584"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "691011584"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3026819481"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "509"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "lion"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_user",
          "value" : "metastore"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-34ef6817bc7dce517d75c76fea2db1e7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "48a01078-dfc2-4b57-8b3d-d07b7cd12c9a"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-6a094bc6eaba971db536a7059f0ed9ff",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "00f946f8-97ca-47e9-8f7f-d5be1482c350"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-ab162b5e9d62f403d980181297543801",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "4305ebd2-6685-451e-9443-fe865f1206a4"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-bfeed17396f5731448367e68127a3f11",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5b2e7ee2-a73e-4c21-ae48-2faf43afc655"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-c2c9702b948bd69c47d98870badccdb7",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-c2c9702b948bd69c47d98870badccdb7",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5ky7pu8ruzq806aymubfv26vs"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-c2c9702b948bd69c47d98870badccdb7",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8sy3lps2kxy732jtj4mj49fho"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896",
    "ipAddress" : "10.0.0.7",
    "hostname" : "elephant",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "5b2e7ee2-a73e-4c21-ae48-2faf43afc655",
    "ipAddress" : "10.0.0.8",
    "hostname" : "horse",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "4305ebd2-6685-451e-9443-fe865f1206a4",
    "ipAddress" : "10.0.0.4",
    "hostname" : "lion",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "48a01078-dfc2-4b57-8b3d-d07b7cd12c9a",
    "ipAddress" : "10.0.0.6",
    "hostname" : "monkey",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "00f946f8-97ca-47e9-8f7f-d5be1482c350",
    "ipAddress" : "10.0.0.5",
    "hostname" : "tiger",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__35b863ee-6775-4a11-ad2d-ed67650472df",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "851328029a2da3a32984f521c2c6ad2f344e269ea6fb597c3465209b56f90e03",
    "pwSalt" : -97173890261246804,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__8ee0004a-d6e8-46f3-ad0a-208435215396",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3425a6f6220f441328353d628f4ddc4fc5bd3c6449b7090aa195dcf474e30f5b",
    "pwSalt" : 8920058726780336672,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-c2c9702b948bd69c47d98870badccdb7",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "aa3f27df1bebfa883956dc6af0566205311e15a13c223968ab77c4f5fb0c437e",
    "pwSalt" : -9084363398083351135,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-c2c9702b948bd69c47d98870badccdb7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c6c5f3d308bd59d4a321c6f0a35e9ea51bc0e961e4b0aee78148de93d48a859b",
    "pwSalt" : -251864721778558361,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-c2c9702b948bd69c47d98870badccdb7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "284ae374b1d1bc5e9a0fb0614758ed5fd3c53f5634d6aeae0b0a3ee40ef4a0eb",
    "pwSalt" : -408884017884360119,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-c2c9702b948bd69c47d98870badccdb7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1633f0350eea0fdec707bfcc2cfdbba12895ee356eec0c27f4afd4141bde0acd",
    "pwSalt" : -478932034996084795,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-c2c9702b948bd69c47d98870badccdb7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e780173fd25f61e52790131628fb30ac16596a49b6d74cad002a7c872a18845d",
    "pwSalt" : 1164093667953151526,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "96e78708c820828c66fc02b167a6a09343dde717dc395fb9c7434f1a3965b8b5",
    "pwSalt" : -7837242499535197670,
    "pwLogin" : true
  }, {
    "name" : "bdany70",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "d1ee6f3995c08ee628f088d5b21c1538ab2ac27a0f20a0a88e8a4a7ff3f4aa0b",
    "pwSalt" : 3348068412823815836,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "71c44cd79edbea532a66236c860c7f2a3f46c77974630326355ca6950413f79c",
    "pwSalt" : 9103421410772799778,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.0",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20171002-1719",
    "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "691011584"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "691011584"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "898629632"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "lion"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "691011584"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "691011584"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "898629632"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-c2c9702b948bd69c47d98870badccdb7",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "eruuqcta441av9nk8xxuizxkf"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-c2c9702b948bd69c47d98870badccdb7",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7gxln588cgfibjn8c0oqmjsit"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-c2c9702b948bd69c47d98870badccdb7",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "5uqoatyfyakt8ahz106xtphv4"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-c2c9702b948bd69c47d98870badccdb7",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dm3x6jx2zgsxcrjavzc1sv0ir"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-c2c9702b948bd69c47d98870badccdb7",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "f7110a39-7b58-450b-9e10-6807b118b896"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "68a3olulkab0vvmbj7upjpeji"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 15:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "http://lion/cloudera-repos/cdh5/parcels/5.13.3/"
    } ]
  }
}
```

