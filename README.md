### 1 Introduction 
Here is the experimental environment and test case used in our Thor demostration.

### 2 Environment
Our Demonstration are conducted on 6 servers connected using 10 Gigabit Ethernet. Each server is equipped with 2 Intel Xeon Silver 4110 @ 2.1 GHz CPUs, 120 GB memory, and 4 TB HDD disk configured in RAID-5 with 4 GB cache. 

### 3 Test Case
#### 3.1 Schema
Thor randomly generates 10 tables. Each table's primary key length is evenly distributed on (1, 2, 3, 4). Each table contains an average of 20 attributes. Data types are evenly distributed on (integer, varchar, double, decimal, blob, timestamp, bool). The number of foreign keys in each table is evenly distributed on (2, 3, 4, 5). The reference relations of foreign keys are evenly distributed on (0,1), the length of foreign keys is evenly distributed on (1,2,3), and the reference relations of foreign keys are evenly distributed to refer to the previously generated table. Each table must be indexed on the primary and foreign keys, and the indexes of other attributes are evenly distributed on (0, 1).

#### 3.2 Data
Each table initializes 100,000 rows of records. The primary key data are evenly distributed on (0,2147483647) and the foreign key data are referenced to the primary key according to the even distribution.For integer, it is evenly distributed on (0,2147483647); for varchar, characters are selected according to uniform distribution, and the length is evenly distributed on (1,200); for double, it is evenly distributed on (-999999.9999,999999.9999); for decimal, it is evenly distributed on (- 99999.99999,99999.9999); for blob, it is evenly distributed on 50 random binary files; for timestamp, a data is randomly added from UTC time, and that data is evenly distributed on (0,2147483647); for bool, it is evenly distributed on (false, true).

#### 3.3 Workload
One workload contains an average of 10 read-write transactions and the other has 10 read-only transactions, both of which contains an average of 20 operations. The operation access distribution is Zipf distribution with parameter skew=1. The test concurrency is 50. The template of basic operations are shown below. 
>**The List of Template of Basic Operation**
>
>| Name of Basic Operation              | Read-Only | Read-Write |
>| ------------------------------------ | --------- | ---------- |
>| key-based_point_read                 | True      | True       |
>| key-based_predicate_read             | True      | True       |
>| foreign-key-based_point_read         | True      | True       |
>| foreign-key-based_predicate_read     | True      | True       |
>| non-key-based_point_read             | True      | True       |
>| non-key-based_predicate_read         | True      | True       |
>| key-based_point_update               | False     | True       |
>| key-based_predicate_update           | False     | True       |
>| foreign-key-based_point_update       | False     | True       |
>| insert                               | False     | True       |
>| delete                               | False     | True       |
>| read-after-update_on_the_same_items  | False     | True       |
>| read-after-insert                    | False     | True       |
>| read-after-delete                    | False     | True       |
>| read-twice_on_the_same_items         | True      | True       |
>| update-two-record_by_foreign_key     | False     | True       |
>| loop                                 | True      | True       |
>| branch                               | True      | True       |
>| active_rollback                      | True      | True       |

##### 3.3.1 Read-Write Transactions
The above operations are selected according to the uniform distribution to form read-write transactions.

##### 3.3.2 Read-Only Transactions
The above operations are selected according to the uniform distribution to form read-only transactions.

##### 3.3.3 Policy of Issuing Transaction 
Thor initializes 50 worker threads that repeatedly issue transactions with a random think time between each request.

### Contact Us
R &amp; D Team: DBhammer project team, School of Data Science & Engineering, East China Normal University.

The main members of the work are: Professor Zhang Rong, Keqiang Li, and Yuming Li.

Address: 3663 Zhongshan North Road, Putuo District, Shanghai.

Postcode: 200062.
