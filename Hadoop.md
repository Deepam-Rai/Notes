# Hadoop

## Book: **_Hadoop: The Definitive Guide by Tom White_** 4th edition

> Hadoop Version - 2

>http://hadoop.apache.org/

> Code Examples: http://hadoopbook.com  
Github: https://github.com/tomwhite/hadoop-book/

> Additional book information: http://bit.ly/hadoop_tdg_4e

<br><br><br>
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
