WARNING
======

This is NOT YET a complete, nor even a very good, PageRank implementation.  This was a learning implementation and, as such, should be treated as a simple learning project.  To speed up calculation speed, it employs multiprocessing, and can be slightly different from single-process results. Use at your own risk.


PageRank
========

   
   [Original Version](https://github.com/timothyasp/PageRank) Thanks to:

   Timothy Asp (@timothyasp)

   Caleb Carlton (@ccarlton)




Run Instructions:
================

NOTE: NetworkX is required for installation. 

```
sudo easy_install networkx
```

For directed data:

```
python pageRank.py <datasource> directed
```

For undirected data:

```
python pageRank.py <datasource> undirected
```

Implementation
=============

Generates a directed or undirected graph of the data, then runs the PageRank algorithm, iterating over every node checking the neighbors (undirected) and out-edges (directed).  We used NetworkX (http://networkx.lanl.gov/) for out graphs which is a great python library for creating and maintaining these graphs.  For D, which is the probability that the user will randomly go to a different page, we chose .85 which is what the book had as the probability for D.  The graph is iterated over 10 times, to calculate the rank best.

Examples
=====
See [examples](examples.md)

 Conclusion
================

PageRank worked well for most of the datasets, but it worked best for datasets with Directed graphs. The results seemed less relevant for undirected graphs because each edge specifies a two way relation between two nodes. Directed graphs are more specific in that a link to a page does not necessarily imply that page links back. For this reason we conclude that pageRank is much more useful on directed graphs.  Also, at first we only iterated over the graph once, but realizing that we need to recalibrate the links after every run, we ran it over the graph multiple times, which yielded much better results.  
