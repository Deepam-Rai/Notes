# Hadoop

## Book: *Hadoop: The Definitive Guide by Tom White* 4th edition
[Extra infos from outside the book are also added in this note.]
> Hadoop Version - 2

>http://hadoop.apache.org/  
> http://www.apache.org/

> Code Examples: http://hadoopbook.com  
Github: https://github.com/tomwhite/hadoop-book/

> Additional book information: http://bit.ly/hadoop_tdg_4e

<br><br><br>

----
# Chapter 1: Meet Hadoop

<!-- #TODO verify -->
>1 Zettabyte = 10<sup>21</sup> Bytes = 2<sup>10</sup>~ 10<sup>3</sup>Exabytes = 2<sup>20</sup>~ 10<sup>6</sup> Petabytes = 2<sup>30</sup>~ 10<sup>9</sup> Terabytes 

## Examples of Big Data
<!-- #TODO find contemporary big data examples -->

>More data usually beats better algorithms. ~ Anand Rajaraman

## Data Storage and Analysis
- The disk read access time hasnt improved overtime, unlike storage capacity.
- More storage hardwares $\implies$ more chances of hardware failure $\implies$ more data loss.
    - Soln: Using redundancy technique like RAID.
- Merging data from different hardwares correctly is challenging - MapReduce solves the problem.  
> Hadoop provides reliable, scalable platform for data storage and analysis, runs on commodity hardware, is opensource and affordable.

## Querying All Your Data
- MapReduce is a _batch_ query processor.
- Can run ad-hoc query on either portion or all of the data.

## Beyond Batch
- Execution of queries takes time - mins.
- Processing pattern that work with Hadoop:
    1. **Interactive SQL**: Instead of MapReduce we can use distributed query engine with always on daemons(like Impala) or container use(like HIVE) which gives us low latency SQL query responses.
    1. **Iterative Processing:** Instead of MapReduce using Spark makes this possible.
    1. **Stream Processing:** Storm, Spark Streaming, Samza
    1. **Search:** Solr runs on Hadoop cluster indexing on documents stored in HDFS.

## Comparison with Other Systems

>**Data locality:** Principle of Hadoop to co-locate data with compute node so that the access of data remains local making access time very low.
### Relational DBMS

| | Traditional RDBMS | MapReduce|
|--|--|--|
|Data Size: | Gigabytes | Petabytes |
|Data Access: | Interactive and Batch | Batch |
|Schema: | Static | Dynamic |
|Updation: | Write Many Read Many times | Write Once Read Many |
|Transactions: | ACID(Atomic, Consistent, Integrity, Durability) | None |
|Integrity: | High | Low|
|Scalability: | Non-Linear | Linear |
|Data type: | Structured | Works well with Unstructured too. |
|Normalization of Data: | Done for integrity and avoid redundancy | Is not done. |

### Grid Computing
| | Grid Computing/HPC(High Performance Computing) | MapReduce |
|--|--|--|
|Data Processing: | Large scale data. | Large scale data. |
|Principle: | Distribute 'work' across cluster accessing data from shared storage. | Distribute 'data' across cluster taking work to where data is.
|Task type: | Fit for computing-intensive tasks. | Better for data-intensive tasks. |
|Storage: | A single shared storage -SAN(Storage Area Network) | Distributed -HDFS. |
|Data Locality: | Not present. | Present. |
|Interface: | MPI(Message Passing Interface) low level with finer control also implying more work for programmer | High level eg MapReduce. |
|Failures: | Programs have to handle explicitly. | MapReduce framework takes care of it.|
|Bottleneck: | Network Bandwidth. | None. |
|Hardware: | Cluster of expensive hardwares. | Cluster of commodity hardwares. |
<!-- #TODO: check hadoop bottleneck -->



### Volunteer Computing
| | Volunteer Computing | MapReduce |
|--|--|--|
|Principle: | Volunteers donate their device CPU cycle for the work whenever idle. | The nodes are engaged for MapReduce totally. |
|Topology: | Cluster of commodity hardware. | Cluster of commodity hardware.|
|Task type: | Compute intensive. | Data intensive. |
|Data Size: | Very small around MBs. | Large around PBs. |
|Data Locality: | Not present. | Present. |
|Resources: | Nodes are donating their CPU cycles. | Nodes are giving their storage, CPU cycles and network badnwidth too. |
|Division: | Works divided into 'work units' which holds data in itself. | Data divided into chunks upon which work is run. |
|Example: | Set@home, Folding@home,etc | MapReduce |

## A Brief History of Apache Hadoop

1. Created by Doug Cutting.
1. Origin of name: Name given by Doug Cutting's kid to stuffed toy elephant.
1. Created as part of Apache Nutch(opensource web search engine) which itself was part of Apache Lucene(text search library created by Doug Cutting).
1. 2002 - Nutch was created, but wasnt very scalable.
1. 2003 - Google's paper on GFS(Google File System) inspired NDFS(Nutch Distributed File System) later renamed as HDFS.
1. 2004 - Google's paper on MapReduce inspired their own MapReduce which was working by 2005.
1. 2006 Feb - MapReduce and NDFS was moved as an independent subproject of Lucene with name Hadoop.
1. Around same time Doug Cutting joined Yahoo! which provided dedicated team for Hadoop to go for web scale.
1. 2008 - Hadoop was made its own top level project at Apache.
1. 2008 -  Hadoop announces that its production search index was being generated by 10,000 core Hadoop cluster.  

<br>
1. 2008 Apr - Hadoop beat previous world record by sorting a TB of data in 209secs.
1. 2008 Nov - Google announced that its MapReduce implementation sorted 1 TB of data in 68secs.
1. 2009 Apr - Hadoop team at Yahoo! sorted 1TB data in 62 secs.



----
# Chapter 2: MapReduce

#TODODefinition:

- Is a framework.
- Is a programming model for data processing.
- Can work with MapReduce program written in various languages.
- Is inherently parallel.
- Has two phases Map and Reduce.
- Framework exposes functions - Map and Reduce, the input and output for both is (key,value) pair.
    - The key and value can be of any datatype or data-structure.
    - This design makes it possible to sequence multiple Map-Reduce.
- Uses HDFS for storage.
## Map
>Definition: Map is the task that is to be run on each chunk of the data in map phase.
- Input and output(s) are (key,value) pair(s).
- They are run on the datanodes that possess the chunks.
- Typically they run parallely on multiple nodes working on different chunks.
- Its output (key,value) pairs are hashed into intermediate files.
- Have the advantage of data locality.
## Intermediate Files
>These are the output files of Map tasks.
- They sit on local file system.
- If there are $r$ reduce tasks, there will be $r$ intermediate output files by **each** map task, thus in total we get (count of map tasks * r) intermediate files.
- number of intermediate files = number of reduce tasks.
- Combiners work upon this intermediate files.
- These files are sent to nodes running the reduce tasks during sort and shuffle phase.

## Combiner
>These are the tasks that are run on the intermediate files.
- By default they are identity function, but Hadoop framework exposes this function for overloading.
- If there are $m$ map tasks, then there will be $m$ combiner functions for each of them.
- **These functions are suitable when the reduce task is associative and commutative.**
- **PURPOSE**: If there are multiple values for a key, then map tasks will create multiple (key, value<sub>i</sub>) pairs, instead of sending these individual pairs we can send (key, [values list or some aggregated value from list of values]) to reduce tasks to save the network bandwidth, these reducing multiple pairs to one pair for a key is done by combiners.

## Sort and Shuffle
1. The combiner works only at the level of each map tasks.
1. At the end of Map phase there are intermediate files from each map tasks with values for a key distributed across intermediate files.
1. **PURPOSE**: Even after combiner phase the values for a key are distributed across intermediate files, this phase gathers all of them and makes the value list.
1. The inputs are $(key, value_1),(key, value_2),...,(key, value_n) $ from intermediate file**s** and the output is $(key, [value_1, value_2, ...,value_n])$.

## Reduce
>Definition: Reduce is the task that is run on the list of values for a key in reduce phase.
- Input and output(s) are (key,value) pair(s).
- They can be run on any node.
- Typically they are run parallely on multiple nodes working on different keys.
- Dont have the advantage of data locality.

## Data Flow
- **Map Reduce Job Unit:** is a unit of work that client wants to be performed and consists of input data, MapReduce program and configuration instruction.
- The client job is divided into input splits
    - The more the splits -> more parallel computation -> more fine balancing of load -> too many splits increases overhead of managing splits themselves.
    - One map task for each
    - Each split can work on multiple chunks.