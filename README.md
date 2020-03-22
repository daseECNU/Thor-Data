The Specification of Demonstration Settings
Environment. Our experiments are conducted on a cluster with 6 nodes. Each node is equipped with 2 Intel Xeon Silver 4110 @ 2.1 GHz CPUs, 120GB memory and 4 TB HDD disk configured in RAID-5. The cluster is connected using 10 Gigabit Ethernet. 
Workload. In the Demonstration, 10 database schemas are randomly generated, and then 10 read-write transactional workloads and 10 read-only transactional workload are randomly generated for each database schema. Each random database schema contains an average of 10.25 tables, each table contains an average of 12 non primary key attributes and 1.75 foreign keys, and the primary key contains an average of 1.45 primary key attributes. The data types of attributes may be integer type, character type, decimal type, float type, datetime type and bool type. Each random workload contains 9 transactions on average, and the operations in the transactions may be any basic database operations. The workload used for Thor performance test and isolation level correctness test is slightly different. For the former, we need a more general workload to reflect the performance of the database system. For the latter, we need a higher level of concurrency and conflict workload to complete the test. For the latter, only read-write transaction loads are needed without read-only transactional workload. Each workload runs for 20 seconds, that is, the performance evaluation runs for 200 * 20 = 4000 seconds in total, and the isolation level correctness test runs for 100 * 20 = 2000 seconds in total. For performance evaluation, when the random read-write transactional workload is generated, the proportions of 9 single SQL statement basic operations, 2 multiple SQL statement basic operations, branch and loop structures are: 0.25, 0.27, 0.05, 0.03, 0.05, 0.02, 0.03, 0.05, 0.05, 0.05, 0.06, 0.04. For isolation level correctness test, when generating random transactional workload, the proportion of basic operations of 9 single SQL statements is respectively: 0.15, 0.05, 0.15, 0.05, 0.1, 0.1, 0.1, 0.1, 0.1; other proportion is consistent with that when generating performance evaluation read-write transactional workload. For all performance evaluation of database, the isolation level of database is set to read uncommitted, and the test concurrency is 50.
Experimental Data. We show the schema, data, and workload used in demonstration in the Experimental Data.zip file. The Experimental Data.zip file contains three folders, namely, populating database, schema & read-only transactional workload and schema & read-write transactional workload. The populating database folder stores the initialization data of 10 tables in the database, for example, the table files table_0_0_0.txt-table_0_0_7.txt in the db0 folder stores the initialization data of the table_0_0 in the db0 database. The schema & read-only transactional workload folder contains 10 read-only workloads and corresponding schemas, for example, the schema_0_0 corresponding to workload_0_0. The schema & read-write transactional workload folder contains 10 read-write workloads and corresponding schemas, for example, the schema_0_0 corresponding to workload_0_0.


