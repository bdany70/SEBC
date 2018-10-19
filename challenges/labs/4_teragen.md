# HDFS Testing

## command

```
[raffles@bdany70-02 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=6 -Ddfs.blocksize=33554432 51200000 /user/raffles/tgen512
```

## output

```
18/10/19 11:23:37 INFO client.RMProxy: Connecting to ResourceManager at bdany70-01.westeurope.cloudapp.azure.com/10.0.1.4:8032
18/10/19 11:23:38 INFO terasort.TeraGen: Generating 51200000 using 6
18/10/19 11:23:38 INFO mapreduce.JobSubmitter: number of splits:6
18/10/19 11:23:38 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
18/10/19 11:23:38 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539939289741_0003
18/10/19 11:23:38 INFO impl.YarnClientImpl: Submitted application application_1539939289741_0003
18/10/19 11:23:38 INFO mapreduce.Job: The url to track the job: http://bdany70-01.westeurope.cloudapp.azure.com:8088/proxy/application_1539939289741_0003/
18/10/19 11:23:38 INFO mapreduce.Job: Running job: job_1539939289741_0003
18/10/19 11:23:45 INFO mapreduce.Job: Job job_1539939289741_0003 running in uber mode : false
18/10/19 11:23:45 INFO mapreduce.Job:  map 0% reduce 0%
18/10/19 11:24:02 INFO mapreduce.Job:  map 17% reduce 0%
18/10/19 11:24:04 INFO mapreduce.Job:  map 40% reduce 0%
18/10/19 11:24:07 INFO mapreduce.Job:  map 45% reduce 0%
18/10/19 11:24:08 INFO mapreduce.Job:  map 58% reduce 0%
18/10/19 11:24:10 INFO mapreduce.Job:  map 62% reduce 0%
18/10/19 11:24:13 INFO mapreduce.Job:  map 66% reduce 0%
18/10/19 11:24:14 INFO mapreduce.Job:  map 72% reduce 0%
18/10/19 11:24:15 INFO mapreduce.Job:  map 78% reduce 0%
18/10/19 11:24:19 INFO mapreduce.Job:  map 84% reduce 0%
18/10/19 11:24:20 INFO mapreduce.Job:  map 92% reduce 0%
18/10/19 11:24:22 INFO mapreduce.Job:  map 97% reduce 0%
18/10/19 11:24:24 INFO mapreduce.Job:  map 100% reduce 0%
18/10/19 11:24:25 INFO mapreduce.Job: Job job_1539939289741_0003 completed successfully
18/10/19 11:24:25 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=899274
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=511
		HDFS: Number of bytes written=5120000000
		HDFS: Number of read operations=24
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=12
	Job Counters 
		Launched map tasks=6
		Other local map tasks=6
		Total time spent by all maps in occupied slots (ms)=172004
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=172004
		Total vcore-milliseconds taken by all map tasks=172004
		Total megabyte-milliseconds taken by all map tasks=176132096
	Map-Reduce Framework
		Map input records=51200000
		Map output records=51200000
		Input split bytes=511
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1183
		CPU time spent (ms)=108390
		Physical memory (bytes) snapshot=2208956416
		Virtual memory (bytes) snapshot=16652623872
		Total committed heap usage (bytes)=2239758336
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=109963291816450258
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=5120000000

real	0m50.521s
user	0m7.776s
sys	0m0.501s
```

## list

```
[raffles@bdany70-02 ~]$ hdfs dfs -ls /user/raffles/tgen512
Found 7 items
-rw-r--r--   3 raffles shops          0 2018-10-19 11:24 /user/raffles/tgen512/_SUCCESS
-rw-r--r--   3 raffles shops  853333400 2018-10-19 11:24 /user/raffles/tgen512/part-m-00000
-rw-r--r--   3 raffles shops  853333300 2018-10-19 11:24 /user/raffles/tgen512/part-m-00001
-rw-r--r--   3 raffles shops  853333300 2018-10-19 11:24 /user/raffles/tgen512/part-m-00002
-rw-r--r--   3 raffles shops  853333400 2018-10-19 11:24 /user/raffles/tgen512/part-m-00003
-rw-r--r--   3 raffles shops  853333300 2018-10-19 11:24 /user/raffles/tgen512/part-m-00004
-rw-r--r--   3 raffles shops  853333300 2018-10-19 11:24 /user/raffles/tgen512/part-m-00005
```

