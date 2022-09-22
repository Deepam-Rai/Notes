# Book: *Mining of Massive Datasets* by Jure Leskovec, Anand Rajaraman and Jeffrey D. Ullaman

# Chapter 1: Data Mining

### **What is data mining?**  
It is the process of analyzing large data sets in order to extract meaningful patterns and trends of the data.

## Bonferroni's Principle
### Motivation:
1. If you are looking for certain types of events in the data, then even if the data is totally random that certain event can occur.
1. As the data size grows the occurrences of these event also grows.
1. But these occurrences are bogus.
1. Bonferroni's principle helps us avoid these random bogus occurrences.

### Informal statement:
1. Calculate the expected number of random occurrences of the event.
1. If this expected number if more than the expected genuine occurrences then any occurrence we find might be bogus-statistical artifact.

## TF.IDF (Term Frequency times Inverse Document Frequency)

>**Stop words:** Common words in English. e.g, the,an,a,are,etc.

> Let,  
> $N$=Number of documents.  
> $f_{ij}$ = frequency of term $i$ in document $j$.  
> $\Large TF_{ij}= \frac{frequency\ of\ term\ i\ in\ document\ j}{frequency\ of\ maximum\ occurring\ term\ in\ the\ same\ document}=\frac{f_{ij}}{max_k f_{kj}}$  
> $\Large IDF_{ij}= \log_2(\frac{N}{number\ of\ documents\ in\ which\ term\ i\ occurs})$  
> $\Large TF.IDF_{ij}=TF_{ij}*IDF_{ij}$  

- The most frequent term in the document gets the TF of 1, other terms in the document get fractions.

## Hash functions
Takes in hash-key and creates a bucket number.

Properties of proper hash-functions:
1. It should have no bias.
1. The hash function should distribute hash-keys evenly in the buckets.
    - Doesn't hold when the number of hash-keys are less than number of buckets.

<!-- #TODO: Rest of chap-1 -->
# Chapter 2: Map Reduce

Points:
- Utilizes parallelism.
- Cluster of commodity hardware.
- Distributed File System.
    - Redundancy, Replication for reliability.

## Physical organization of compute nodes - Cluster Computing
- Computer nodes are stored on rack**s**.
- **Intra rack switch:** Communication within the rack.
- **Inter rack switch:** Communication among the racks.
    - Typically has more bandwidth than intra-rack switch.
    - Can cause the whole cluster communication to fail.
- More number of components => More chances of component failure.
- Files:
    - Stored redundantly - inter-rack preferred.
    - Stored as **chunks**.
    - Chunks are further collection of **elements** - the unit of files that cannot be divided(can be of any data type).
- Computations divided into tasks - independent & parallel.
- **DFS(Distributed File System):**
    - Implementations: GFS(Google File System), HDFS(Hadoop Distributed FIle System), Cloudstore.
    - Write once read many times type.
    - Master node/Name node:
        - The node which can direct to the nodes storing the chunks.
        - Need not necessarily store metadata/schema - eg HDFS.
        - Is itself replicated.

## MapReduce
- A style of computing.
- **REFER TO HADOOP NOTES.**

## Coping with Failures

### Resilience of Namenodes
Name node maintains
1. Namespace image
    - Shifted from HDFS to in-memory on initiation.
2. Eit logs
    - log the files and perform action in-memory in namespace image in RAM[not being written to disk]  

- Name-node can become Single Point of Failure.  

**Metadata:**
- Nodes for the data-blocks are obtained by name-node communicating with datanodes on **startup**.
- Periodically updated by datablock to the namenode - in pulses.  

Mitigation of SPOF:
1. Another robust filesystem for name-node writes eg NFS(Network File System).
1. Secondary namenode
    - Periodically merges in-memory namespace image and -logs.
1. HDFS Federation: namespace division
    - different namenode for different branch of file hierarchy.
1. High availability: multiple active name-node.

### Failure of workernodes
- namenode periodically pings worker nodes or vice versa as pulses, stopping of it for several beats signals failure of workernodes.
- On failure simply set status of the job to idle and reschedule to another node.

## **Algorithms**

### **Matrix A and Vector v multiplication**
#### 1. The vector 'v' fits into memory  
<pre>
Map( ((i,j,A<sub>ij</sub>),(i,j,A<sub>ij</sub>)))  
{  
   Output( (i, A<sub>ij</sub>*V<sub>j</sub>))  
}
Reduce( (i, [A<sub>ij</sub>*V<sub>j</sub> for i,j=1,2,..,n]))
{
    #sum of all the values
    e=0
    for each e in value-list
    {
        sum +=e
    }
    Output( (i, sum))
}
</pre>
#### 2. The vector V does not fit into the memory
 **Solution:** Partition the vector and matrix.
 - When the map works with a partition of matrix it will load appropriate partition of vector into memory.
 - When the corresponding partition of vector is present in the memory the previous algorithm can follow.
 ![Partition of matrix and vector, when vector doesnt fit in memory]( ./Images/Big%20Data/Partition_of_vector_and_matrix.png "Partition of matrix and vector, when vector doesnt fit in memory")

 ### **Relational Algebra**
Table $\to$ Relation
Rows $\to$ Tuples  
Columns $\to$ Attributes  
Set of Attributes of Relation $\to$ Schema

1. Selection $\sigma_C(R)$: Get those tuples in relation-R which satisfies condition c.
<pre>
Map( (t,c))
{
    if (t satisfies condition c)
    {
        Output( (t,t))
    }
    else
    {
        Output( (None,None)) #Map HAS to produce (key,value) output
    }
}
Reduce( (t, [t,t,...,t]))
{
    Output( (t,t))
}
</pre>
2. Projection
<pre>
Map( (t,s))
{
    ts <- subset of 't' containing only 's' attributes
    Output( (ts,ts))
}
Reduce( (ts, [ts, ts, ..., ts]))
{
    Output( (ts,ts))
}
</pre>
3. Union
<pre>
Map(t,R)
{
    Output( (t,(t,R)))
}
Reduce( (t, [ (t,A),(t,A),...,(t,A), (t,B),(t,B),...,(t,B)]))
{
    #For each pair of 't' from A and B there will be one pair in output.
    #Any extra 't' in A or B, it will be put just as it is.
    
    countA = count of (t,A) in input value-list
    countB = count of (t,B) in input value-list

    for i in range(1 to  max(countA, countB))
    {
        Output( (t,t))
    }
}
</pre>
4. Intersection
<pre>
Map -> Identity
Reduce( (t,[A,A,...,A,B,B,...,B]))
{
    countA = count of 'A' in value-list
    countB = count of 'B' in value-list
    if (countA>0 and countB>0)  #if tuple 't' exists in both A and B
    {
        for i in range(1 to min(countA,countB))
        {
            Output( (t,t))
        }
    }
}
</pre>
5. Difference
<pre>
Map-> Identity
Reduce( (t,[A,A,...,A,B,B,...,B]))
{
    countA = count of 'A' in value-list
    countB = count of 'B' in value-list
    if (countA > countB)
    {
        for i in range(1 to (countA-countB))
        {
            Output( (t,t))
        }
    }
}
</pre>
6. #TODO:Grouping and Aggregation
7. #TODO:Natural Join

