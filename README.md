# TripleBit
TripleBit, a fast and compact system for large scale RDF graph. 

TripeBit is designed based on two important observations. First, it is important to design a storage structure that can directly and efficiently query the RDF graph. This motivates us to design a compact storage and index structure in TripleBit. Second, in order to truly scale the RDF query processor, we need efficient index structures and query evaluation algorithms to minimize the size of intermediate results generated when evaluating queries, especially complex join queries. This leads us to the design decision that we should not only reduce the size of indexes (e.g., through compression techniques) but also minimize the number of indexes used in query evaluation.


