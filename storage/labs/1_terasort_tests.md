### Create user bdany70 in every node

```shell
[root@tiger ~]# adduser bdany70
```

### Change permission on HDFS

```shell
hdfs@elephant ~]$ hdfs dfs -chown -R bdany70:bdany70 /user/bdany70
[hdfs@elephant ~]$ hdfs dfs -ls /user/bdany70
Found 1 items
drwxr-xr-x   - bdany70 bdany70          0 2018-10-16 04:22 /user/bdany70/unsorted
```

### Generate 10GB file

```shell
[hdfs@elephant ~]$ logout
[root@elephant ~]# su - bdany70
[bdany70@elephant ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -Dmapred.map.tasks=1 -Ddfs.block.size=33554432 104857600  /user/bdany70/unsorted-1
18/10/16 08:05:44 INFO client.RMProxy: Connecting to ResourceManager at elephant/10.0.0.7:8032
18/10/16 08:05:45 INFO terasort.TeraGen: Generating 104857600 using 1
18/10/16 08:05:45 INFO mapreduce.JobSubmitter: number of splits:1
18/10/16 08:05:45 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
18/10/16 08:05:45 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
18/10/16 08:05:45 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539683823019_0004
18/10/16 08:05:46 INFO impl.YarnClientImpl: Submitted application application_1539683823019_0004
18/10/16 08:05:46 INFO mapreduce.Job: The url to track the job: http://elephant:8088/proxy/application_1539683823019_0004/
18/10/16 08:05:46 INFO mapreduce.Job: Running job: job_1539683823019_0004
18/10/16 08:05:53 INFO mapreduce.Job: Job job_1539683823019_0004 running in uber mode : false
18/10/16 08:05:53 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 08:06:10 INFO mapreduce.Job:  map 9% reduce 0%
18/10/16 08:06:16 INFO mapreduce.Job:  map 14% reduce 0%
18/10/16 08:06:22 INFO mapreduce.Job:  map 19% reduce 0%
18/10/16 08:06:28 INFO mapreduce.Job:  map 24% reduce 0%
18/10/16 08:06:34 INFO mapreduce.Job:  map 28% reduce 0%
18/10/16 08:06:40 INFO mapreduce.Job:  map 29% reduce 0%
18/10/16 08:06:46 INFO mapreduce.Job:  map 34% reduce 0%
18/10/16 08:06:52 INFO mapreduce.Job:  map 39% reduce 0%
18/10/16 08:06:58 INFO mapreduce.Job:  map 44% reduce 0%
18/10/16 08:07:04 INFO mapreduce.Job:  map 48% reduce 0%
18/10/16 08:07:09 INFO mapreduce.Job:  map 52% reduce 0%
18/10/16 08:07:15 INFO mapreduce.Job:  map 56% reduce 0%
18/10/16 08:07:21 INFO mapreduce.Job:  map 59% reduce 0%
18/10/16 08:07:27 INFO mapreduce.Job:  map 63% reduce 0%
18/10/16 08:07:33 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 08:07:39 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 08:07:45 INFO mapreduce.Job:  map 76% reduce 0%
18/10/16 08:07:51 INFO mapreduce.Job:  map 79% reduce 0%
18/10/16 08:07:58 INFO mapreduce.Job:  map 82% reduce 0%
18/10/16 08:08:04 INFO mapreduce.Job:  map 85% reduce 0%
18/10/16 08:08:10 INFO mapreduce.Job:  map 89% reduce 0%
18/10/16 08:08:16 INFO mapreduce.Job:  map 95% reduce 0%
18/10/16 08:08:22 INFO mapreduce.Job:  map 99% reduce 0%
18/10/16 08:08:23 INFO mapreduce.Job:  map 100% reduce 0%
18/10/16 08:08:24 INFO mapreduce.Job: Job job_1539683823019_0004 completed successfully
18/10/16 08:08:24 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=147626
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=83
		HDFS: Number of bytes written=10485760000
		HDFS: Number of read operations=4
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=2
	Job Counters 
		Launched map tasks=1
		Other local map tasks=1
		Total time spent by all maps in occupied slots (ms)=147903
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=147903
		Total vcore-milliseconds taken by all map tasks=147903
		Total megabyte-milliseconds taken by all map tasks=151452672
	Map-Reduce Framework
		Map input records=104857600
		Map output records=104857600
		Input split bytes=83
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=624
		CPU time spent (ms)=147240
		Physical memory (bytes) snapshot=212008960
		Virtual memory (bytes) snapshot=2811842560
		Total committed heap usage (bytes)=154664960
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=225186913807133164
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10485760000

real	2m42.437s
user	0m8.778s
sys	0m0.688s
[bdany70@elephant ~]$ hdfs dfs -ls
Found 3 items
drwx------   - bdany70 bdany70          0 2018-10-16 08:08 .staging
drwxr-xr-x   - bdany70 bdany70          0 2018-10-16 04:22 unsorted
drwxr-xr-x   - bdany70 bdany70          0 2018-10-16 08:08 unsorted-1
[bdany70@elephant ~]$ hdfs dfs -ls unsorted-1
Found 2 items
-rw-r--r--   3 bdany70 bdany70           0 2018-10-16 08:08 unsorted-1/_SUCCESS
-rw-r--r--   3 bdany70 bdany70 10485760000 2018-10-16 08:08 unsorted-1/part-m-00000
[bdany70@elephant ~]$ hdfs dfs -ls -h unsorted-1
Found 2 items
-rw-r--r--   3 bdany70 bdany70           0 2018-10-16 08:08 unsorted-1/_SUCCESS
-rw-r--r--   3 bdany70 bdany70       9.8 G 2018-10-16 08:08 unsorted-1/part-m-00000
```

### Sort 10GB file

```shell
[bdany70@elephant ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/bdany70/unsorted-1 /user/bdany70/sorted
18/10/16 08:17:02 INFO terasort.TeraSort: starting
18/10/16 08:17:04 INFO input.FileInputFormat: Total input paths to process : 1
Spent 275ms computing base-splits.
Spent 9ms computing TeraScheduler splits.
Computing input splits took 285ms
Sampling 10 splits of 313
Making 8 from 100000 sampled records
Computing parititions took 823ms
Spent 1111ms computing partitions.
18/10/16 08:17:05 INFO client.RMProxy: Connecting to ResourceManager at elephant/10.0.0.7:8032
18/10/16 08:17:05 INFO mapreduce.JobSubmitter: number of splits:313
18/10/16 08:17:06 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1539683823019_0005
18/10/16 08:17:06 INFO impl.YarnClientImpl: Submitted application application_1539683823019_0005
18/10/16 08:17:06 INFO mapreduce.Job: The url to track the job: http://elephant:8088/proxy/application_1539683823019_0005/
18/10/16 08:17:06 INFO mapreduce.Job: Running job: job_1539683823019_0005
18/10/16 08:17:13 INFO mapreduce.Job: Job job_1539683823019_0005 running in uber mode : false
18/10/16 08:17:13 INFO mapreduce.Job:  map 0% reduce 0%
18/10/16 08:17:21 INFO mapreduce.Job:  map 1% reduce 0%
18/10/16 08:17:26 INFO mapreduce.Job:  map 3% reduce 0%
18/10/16 08:17:27 INFO mapreduce.Job:  map 4% reduce 0%
18/10/16 08:17:29 INFO mapreduce.Job:  map 5% reduce 0%
18/10/16 08:17:36 INFO mapreduce.Job:  map 6% reduce 0%
18/10/16 08:17:37 INFO mapreduce.Job:  map 7% reduce 0%
18/10/16 08:17:38 INFO mapreduce.Job:  map 8% reduce 0%
18/10/16 08:17:39 INFO mapreduce.Job:  map 10% reduce 0%
18/10/16 08:17:47 INFO mapreduce.Job:  map 11% reduce 0%
18/10/16 08:17:48 INFO mapreduce.Job:  map 12% reduce 0%
18/10/16 08:17:50 INFO mapreduce.Job:  map 14% reduce 0%
18/10/16 08:17:52 INFO mapreduce.Job:  map 15% reduce 0%
18/10/16 08:17:59 INFO mapreduce.Job:  map 16% reduce 0%
18/10/16 08:18:00 INFO mapreduce.Job:  map 17% reduce 0%
18/10/16 08:18:02 INFO mapreduce.Job:  map 18% reduce 0%
18/10/16 08:18:03 INFO mapreduce.Job:  map 19% reduce 0%
18/10/16 08:18:05 INFO mapreduce.Job:  map 20% reduce 0%
18/10/16 08:18:10 INFO mapreduce.Job:  map 21% reduce 0%
18/10/16 08:18:11 INFO mapreduce.Job:  map 22% reduce 0%
18/10/16 08:18:14 INFO mapreduce.Job:  map 23% reduce 0%
18/10/16 08:18:15 INFO mapreduce.Job:  map 24% reduce 0%
18/10/16 08:18:17 INFO mapreduce.Job:  map 25% reduce 0%
18/10/16 08:18:21 INFO mapreduce.Job:  map 26% reduce 0%
18/10/16 08:18:22 INFO mapreduce.Job:  map 27% reduce 0%
18/10/16 08:18:26 INFO mapreduce.Job:  map 28% reduce 0%
18/10/16 08:18:28 INFO mapreduce.Job:  map 29% reduce 0%
18/10/16 08:18:29 INFO mapreduce.Job:  map 30% reduce 0%
18/10/16 08:18:32 INFO mapreduce.Job:  map 31% reduce 0%
18/10/16 08:18:35 INFO mapreduce.Job:  map 32% reduce 0%
18/10/16 08:18:38 INFO mapreduce.Job:  map 33% reduce 0%
18/10/16 08:18:39 INFO mapreduce.Job:  map 34% reduce 0%
18/10/16 08:18:42 INFO mapreduce.Job:  map 35% reduce 0%
18/10/16 08:18:44 INFO mapreduce.Job:  map 36% reduce 0%
18/10/16 08:18:48 INFO mapreduce.Job:  map 37% reduce 0%
18/10/16 08:18:50 INFO mapreduce.Job:  map 38% reduce 0%
18/10/16 08:18:51 INFO mapreduce.Job:  map 39% reduce 0%
18/10/16 08:18:54 INFO mapreduce.Job:  map 41% reduce 0%
18/10/16 08:18:56 INFO mapreduce.Job:  map 42% reduce 0%
18/10/16 08:19:02 INFO mapreduce.Job:  map 43% reduce 0%
18/10/16 08:19:03 INFO mapreduce.Job:  map 44% reduce 0%
18/10/16 08:19:04 INFO mapreduce.Job:  map 45% reduce 0%
18/10/16 08:19:06 INFO mapreduce.Job:  map 46% reduce 0%
18/10/16 08:19:08 INFO mapreduce.Job:  map 47% reduce 0%
18/10/16 08:19:14 INFO mapreduce.Job:  map 50% reduce 0%
18/10/16 08:19:18 INFO mapreduce.Job:  map 51% reduce 0%
18/10/16 08:19:22 INFO mapreduce.Job:  map 52% reduce 0%
18/10/16 08:19:25 INFO mapreduce.Job:  map 53% reduce 0%
18/10/16 08:19:26 INFO mapreduce.Job:  map 55% reduce 0%
18/10/16 08:19:28 INFO mapreduce.Job:  map 56% reduce 0%
18/10/16 08:19:32 INFO mapreduce.Job:  map 57% reduce 0%
18/10/16 08:19:36 INFO mapreduce.Job:  map 58% reduce 0%
18/10/16 08:19:38 INFO mapreduce.Job:  map 60% reduce 0%
18/10/16 08:19:40 INFO mapreduce.Job:  map 61% reduce 0%
18/10/16 08:19:45 INFO mapreduce.Job:  map 62% reduce 0%
18/10/16 08:19:47 INFO mapreduce.Job:  map 63% reduce 0%
18/10/16 08:19:50 INFO mapreduce.Job:  map 65% reduce 0%
18/10/16 08:19:53 INFO mapreduce.Job:  map 66% reduce 0%
18/10/16 08:19:54 INFO mapreduce.Job:  map 67% reduce 0%
18/10/16 08:19:58 INFO mapreduce.Job:  map 68% reduce 0%
18/10/16 08:20:02 INFO mapreduce.Job:  map 70% reduce 0%
18/10/16 08:20:04 INFO mapreduce.Job:  map 71% reduce 0%
18/10/16 08:20:06 INFO mapreduce.Job:  map 72% reduce 0%
18/10/16 08:20:09 INFO mapreduce.Job:  map 73% reduce 0%
18/10/16 08:20:13 INFO mapreduce.Job:  map 74% reduce 0%
18/10/16 08:20:14 INFO mapreduce.Job:  map 75% reduce 0%
18/10/16 08:20:17 INFO mapreduce.Job:  map 76% reduce 0%
18/10/16 08:20:18 INFO mapreduce.Job:  map 77% reduce 0%
18/10/16 08:20:19 INFO mapreduce.Job:  map 78% reduce 0%
18/10/16 08:20:24 INFO mapreduce.Job:  map 79% reduce 0%
18/10/16 08:20:26 INFO mapreduce.Job:  map 80% reduce 0%
18/10/16 08:20:29 INFO mapreduce.Job:  map 81% reduce 0%
18/10/16 08:20:30 INFO mapreduce.Job:  map 82% reduce 0%
18/10/16 08:20:31 INFO mapreduce.Job:  map 83% reduce 0%
18/10/16 08:20:36 INFO mapreduce.Job:  map 84% reduce 0%
18/10/16 08:20:37 INFO mapreduce.Job:  map 85% reduce 0%
18/10/16 08:20:46 INFO mapreduce.Job:  map 86% reduce 0%
18/10/16 08:20:49 INFO mapreduce.Job:  map 86% reduce 4%
18/10/16 08:20:50 INFO mapreduce.Job:  map 87% reduce 4%
18/10/16 08:20:51 INFO mapreduce.Job:  map 87% reduce 10%
18/10/16 08:20:52 INFO mapreduce.Job:  map 87% reduce 14%
18/10/16 08:20:53 INFO mapreduce.Job:  map 88% reduce 18%
18/10/16 08:20:57 INFO mapreduce.Job:  map 88% reduce 21%
18/10/16 08:20:58 INFO mapreduce.Job:  map 88% reduce 23%
18/10/16 08:21:01 INFO mapreduce.Job:  map 89% reduce 23%
18/10/16 08:21:03 INFO mapreduce.Job:  map 89% reduce 25%
18/10/16 08:21:04 INFO mapreduce.Job:  map 90% reduce 26%
18/10/16 08:21:09 INFO mapreduce.Job:  map 91% reduce 26%
18/10/16 08:21:13 INFO mapreduce.Job:  map 92% reduce 26%
18/10/16 08:21:15 INFO mapreduce.Job:  map 93% reduce 27%
18/10/16 08:21:19 INFO mapreduce.Job:  map 94% reduce 27%
18/10/16 08:21:23 INFO mapreduce.Job:  map 95% reduce 27%
18/10/16 08:21:26 INFO mapreduce.Job:  map 96% reduce 27%
18/10/16 08:21:27 INFO mapreduce.Job:  map 96% reduce 28%
18/10/16 08:21:31 INFO mapreduce.Job:  map 97% reduce 28%
18/10/16 08:21:35 INFO mapreduce.Job:  map 98% reduce 28%
18/10/16 08:21:38 INFO mapreduce.Job:  map 99% reduce 28%
18/10/16 08:21:39 INFO mapreduce.Job:  map 99% reduce 29%
18/10/16 08:21:40 INFO mapreduce.Job:  map 100% reduce 29%
18/10/16 08:21:43 INFO mapreduce.Job:  map 100% reduce 31%
18/10/16 08:21:45 INFO mapreduce.Job:  map 100% reduce 42%
18/10/16 08:21:46 INFO mapreduce.Job:  map 100% reduce 49%
18/10/16 08:21:47 INFO mapreduce.Job:  map 100% reduce 54%
18/10/16 08:21:49 INFO mapreduce.Job:  map 100% reduce 57%
18/10/16 08:21:51 INFO mapreduce.Job:  map 100% reduce 61%
18/10/16 08:21:52 INFO mapreduce.Job:  map 100% reduce 64%
18/10/16 08:21:53 INFO mapreduce.Job:  map 100% reduce 65%
18/10/16 08:21:54 INFO mapreduce.Job:  map 100% reduce 70%
18/10/16 08:21:55 INFO mapreduce.Job:  map 100% reduce 71%
18/10/16 08:21:57 INFO mapreduce.Job:  map 100% reduce 75%
18/10/16 08:21:58 INFO mapreduce.Job:  map 100% reduce 78%
18/10/16 08:21:59 INFO mapreduce.Job:  map 100% reduce 79%
18/10/16 08:22:00 INFO mapreduce.Job:  map 100% reduce 84%
18/10/16 08:22:01 INFO mapreduce.Job:  map 100% reduce 86%
18/10/16 08:22:02 INFO mapreduce.Job:  map 100% reduce 88%
18/10/16 08:22:03 INFO mapreduce.Job:  map 100% reduce 90%
18/10/16 08:22:04 INFO mapreduce.Job:  map 100% reduce 92%
18/10/16 08:22:06 INFO mapreduce.Job:  map 100% reduce 94%
18/10/16 08:22:09 INFO mapreduce.Job:  map 100% reduce 96%
18/10/16 08:22:10 INFO mapreduce.Job:  map 100% reduce 97%
18/10/16 08:22:11 INFO mapreduce.Job:  map 100% reduce 98%
18/10/16 08:22:13 INFO mapreduce.Job:  map 100% reduce 99%
18/10/16 08:22:15 INFO mapreduce.Job:  map 100% reduce 100%
18/10/16 08:22:16 INFO mapreduce.Job: Job job_1539683823019_0005 completed successfully
18/10/16 08:22:16 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=4695483328
		FILE: Number of bytes written=9330718882
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10485798186
		HDFS: Number of bytes written=10485760000
		HDFS: Number of read operations=963
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=313
		Launched reduce tasks=8
		Data-local map tasks=313
		Total time spent by all maps in occupied slots (ms)=2897294
		Total time spent by all reduces in occupied slots (ms)=693403
		Total time spent by all map tasks (ms)=2897294
		Total time spent by all reduce tasks (ms)=693403
		Total vcore-milliseconds taken by all map tasks=2897294
		Total vcore-milliseconds taken by all reduce tasks=693403
		Total megabyte-milliseconds taken by all map tasks=2966829056
		Total megabyte-milliseconds taken by all reduce tasks=710044672
	Map-Reduce Framework
		Map input records=104857600
		Map output records=104857600
		Map output bytes=10695475200
		Map output materialized bytes=4587320889
		Input split bytes=38186
		Combine input records=0
		Combine output records=0
		Reduce input groups=104857600
		Reduce shuffle bytes=4587320889
		Reduce input records=104857600
		Reduce output records=104857600
		Spilled Records=209715200
		Shuffled Maps =2504
		Failed Shuffles=0
		Merged Map outputs=2504
		GC time elapsed (ms)=61263
		CPU time spent (ms)=1596720
		Physical memory (bytes) snapshot=157903265792
		Virtual memory (bytes) snapshot=891870642176
		Total committed heap usage (bytes)=162827599872
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10485760000
	File Output Format Counters 
		Bytes Written=10485760000
18/10/16 08:22:16 INFO terasort.TeraSort: done

real	5m15.071s
user	0m11.244s
sys	0m0.831s

```

