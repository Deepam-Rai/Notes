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

