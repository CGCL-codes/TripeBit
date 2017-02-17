# TripleBit
TripleBit, a fast and compact system for large scale RDF graph. 

TripeBit is designed based on two important observations. First, it is important to design a storage structure that can directly and efficiently query the RDF graph. This motivates us to design a compact storage and index structure in TripleBit. Second, in order to truly scale the RDF query processor, we need efficient index structures and query evaluation algorithms to minimize the size of intermediate results generated when evaluating queries, especially complex join queries. This leads us to the design decision that we should not only reduce the size of indexes (e.g., through compression techniques) but also minimize the number of indexes used in query evaluation.


TripleBit
(c) 2011 Massive Data Management Group @ SCTS & CGCL. 
	Web site: http://grid.hust.edu.cn/triplebit

This work is licensed under the Creative Commons
Attribution-Noncommercial-Share Alike 3.0 Unported License. To view a copy
of this license, visit http://creativecommons.org/licenses/by-nc-sa/3.0/
or send a letter to Creative Commons, 171 Second Street, Suite 300,
San Francisco, California, 94105, USA.


Dependency:
-----------
Please install boost, you can use the following version or other version. [boost_1_46_1.tar.gz](http://grid.hust.edu.cn/triplebit/boost_1_46_1.tar.gz) next lines are the way to install boost<br>

`tar -zxvf boost_1_46_1.tar.gz`<br>
`cd boost_1_46_1` <br>
`./bootstrap.sh` <br>
`./bjam` <br>
`cp -r boost/ /usr/local/include/` <br>

Building:
---------

TripleBit must be build using GNU make and a reasonable C++ compiler. Ideally a simple  "`make`" is enough, it will build the tree high-level executables in bin/lrelease/.


Using:
------

TripleBit currently includes two high-level executables. The first (buildTripleBitFromN3)
is used to build a new database from an turtle/ntriples input: <br>

   `buildTripleBitFromN3 mydata.n3 database_directory`

The input file can be arbitrarily large, the buildTripleBitFromN3 spools to disk if
main memory is exhausted.<br>

After loading the database can be queried with triplebitQuery: <br>

   `triplebitQuery database_directory query_directory`

The program shows a command prompt and accept SPARQL queries.<br>

Note: TripleBit currently only supports "select" queries.



Publication:
------

Pingpeng Yuan, Pu Liu, Buwen Wu, Ling Liu, Hai Jin, and Wenya Zhang. [TripleBit: a Fast and Compact System for Large Scale RDF Data.](http://grid.hust.edu.cn/triplebit/TripleBit_VLDB2013.pdf) PVLDB, 6(7):517-528, 2013.<br>
Buwen Wu, Yongluan Zhou, Pingpeng Yuan, Hai Jin, Ling Liu. [SemStore: A Semantic-Preserving Distributed RDF Triple Store.](http://grid.hust.edu.cn/triplebit/SemStore_CIKM2014.pdf) CIKM 2014, Shanghai, China, Nov 3-7, 2014.<br>
Pingpeng Yuan, Wenya Zhang, Changfeng Xie, Ling Liu, Hai Jin, Kisung Lee. [Fast Iterative Graph Computation: A Path Centric Approach.](http://grid.hust.edu.cn/triplebit/PathGraph_SC2014.pdf) SC 2014, New Orleans, USA, Nov.16-21, 2014.<br>
Buwen Wu, Yongluan Zhou, Pingpeng Yuan, Ling Liu and Hai Jin. [Scalable SPARQL Querying using Path Partitioning.](http://grid.hust.edu.cn/triplebit/icde2015-Wu.pdf) ICDE 2015, Seoul, Korea, April 13-16, 2015.<br>



Useful Link:
------
[TripleBit FAQ](http://grid.hust.edu.cn/triplebit/faq.html)<br>
[LUBM](http://swat.cse.lehigh.edu/projects/lubm/)<br>
[Uniprot](http://www.uniprot.org/) & [Uniprot Dataset](ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/rdf/)<br>
[BTC](http://km.aifb.kit.edu/projects/btc-2012/)<br>
[Dataset Sample](http://grid.hust.edu.cn/triplebit/examples.tar.gz)<br>



Support or Contact
------
TripleBit is developed in the [HUST SCTS&CGCL Lab](http://grid.hust.edu.cn/). If you have any questions, please contact Pingpeng Yuan(ppyuan@hust.edu.cn). We welcome you to commit your modification to support our project.
