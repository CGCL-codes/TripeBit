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
Please install boost, you can use the following version or other version.

boost_1_46_1.tar.gz

next lines are the way to install boost
# tar -zxvf boost_1_46_1.tar.gz
# cd boost_1_46_1
# ./bootstrap.sh
# ./bjam
# cp -r boost/ /usr/local/include/

Building:
---------

TripleBit must be build using GNU make and a reasonable C++ compiler. Ideally a simple

   make

is enough, it will build the tree high-level executables in bin/lrelease/.

Using:
------

TripleBit currently includes two high-level executables. The first (buildTripleBitFromN3)
is used to build a new database from an turtle/ntriples input:

   buildTripleBitFromN3 mydata.n3 database_directory

The input file can be arbitrarily large, the buildTripleBitFromN3 spools to disk if
main memory is exhausted.

After loading the database can be queried with triplebitQuery:

   triplebitQuery database_directory query_directory

The program shows a command prompt and accept SPARQL queries.

Note: TripleBit currently only supports "select" queries.
