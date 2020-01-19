--- 
layout: default
title: GNOWSYS 
description: A Project of Gnowledge Lab of HBCSE, TIFR
---
{% include menu.html %}

# GNOWSYS and Gstudio


![GNOWSYS logo](https://www.gnu.org/software/gnowsys/gnowsys-logo-revised-small.png)

### Introduction to GNOWSYS

GNOWSYS is a specification for a generic distributed network based
memory/knowledge management. Typically computer memory is managed as a
tree, or as nested arrays. Our attempt in this project is to represent
all forms of declarative and procedural knowledge as a network, and then
develop network processing methods to create and publish knowledge as a
network.

![GNOWSYS](https://stemgames.metastudio.org/uploads/default/original/2X/e/ec4d81cc161b4732d7b927b1ef5100116c5a911d.png)


### Node orientated computing

Just as the language LISP provides list oriented computing framework, we
try to model the knowledge as *nodes in a network*. The interpretation
(meaning) of a node depends on the links the node has with other nodes,
and the interpretation of the other *neighbouring* nodes in turn depends
on their network and so on. The nodes are organized and processed
according to a complex data structure called the *neighborhood*, akin to
a frame.

The network is constructed by interlinking all things to those whose
interpretation is implicitly available to the computing system. Those
nodes whose interpretation is known to the computing system may be
called as *primitive nodes* since they are made available as the initial
condition of the evolving semantic system. They may be also called as
the *factory nodes*. Such nodes become the *meaning mediators* in the
semantic system.

These primitives can be further devided into *logical types* and *data
types*. The most commonly used semantic relations like \"type of\" and
\"member of\" are the logical types, while the character set, numbers
and other models of structured symbol sets with known interpretation are
the data types. Thus the nodes in a network will be constructed with the
known logical and data types.

New nodes obtain their meaning due to their relations with the
primitives. That is by linking unknown symbols with known symbols
GNOWSYS provides a mechanism to define new meaning from the already
available meaning. The variety of possible meaning space depends
entirely on the chosen primitive set of nodes.


### The Structure of the Network Memory

The network construction uses the following principles:

1.  Everything is a node. The memory in GNOWSYS is a set of nodes with
    all nodes with a unique NID (Node ID). The NID with the address
    locator gives rise to a unique URI in the cyberspace.
2.  A node links with the neighborhood nodes through relations, and some
    predefined name and value pairs called attributes.
3.  Every node is described/interpreted by neighborhood, which is
    nothing but the set of relations and attributes a node possesses.
    This can be rendered as a context graph.
4.  A network can be obtained by merging the neighborhood of all the
    nodes as a graph.
5.  The set of all attributes and relations is the full set of knowledge
    represented in the network in the form of propositions.
6.  Each attribute or relation constitutes one
    [RDF](http://www.w3.org/TR/rdf-concepts/) triple expressing one
    proposition.
7.  The representation of network memory can be completely encoded in
    any of the [RDF](http://www.w3.org/RDF/) notations.

### The Dynamics (change management) of the Network Memory

1.  Insertion of new relations and attributes changes the neighborhood
    of the nodes concerned, and such changes can be tracked by holding
    the snapshots of the node\'s neighborhood at each instance of
    change.
2.  Being a collaborative space, the system records who did what change
    and at what time.
3.  Delinking is the preferred way of removing data elements from the
    network, and no node can be removed without prior removal of the
    links the node may have with others.
4.  Each Node\'s neighborhood at a given time becomes the state space of
    the node.
5.  Changing state of nodes can be recorded, and described as process
    nodes that record the prior-state and post-state of the nodes
    invovled.

### Node types

Based on the type of attributes and relations, we can distinguish some
widely repeated kind of patterns as node types for convenience. These
node types can be used for managing the data of computing applications.
New nodetypes can be defined as and when required, though minimalism is
encouraged for ensuring generality of processing engines and maintaining
parsimony. Currently GNOWSYS has the following node types:

1.  Type Nodes:
    -   Metatype
    -   System Type
    -   Attribute Type
    -   Relation Type
    -   Process Type
2.  Token Nodes:
    -   Systems
    -   Processes
3.  Triples:
    -   Relations
    -   Attributes
4.  Special Derivative Nodes (to be implemented):
    -   Union
    -   Complement
    -   Intersection
5.  Complex Expressions:
    -   Node Specification
    -   Relation Specification
    -   Attribute Specification
    -   Expression

### Acronym

GNOWSYS is an acronym for Gnowledge Networking and Organizing SYStem.
The \'G\' in GNOWSYS is pronounced hard just as the \'G\' in GNU.

### Features Implemented 

The specification is implemented currently in
[Python](http://www.python.org/). The current implementation used
[Django framework](https://www.djangoproject.com/).

Older implementations were done as a product of
[ZOPE](http://www.zope.org/) (Zee Object Publishing Environment), a free
web application framework. These are archived, and no further
development from the main team is expected.

The currently available version (bleeding-edge) of GNOWSYS is
availableas gstudio (short for gnowsys-studio) be obtained from the [git
repository](https://github.com/gnowledge/gstudio). No stable version is released as yet. Docker composer files are available on gitrepo.

If you want to see live implementations, please visit:

- [http://www.metaStudio.org](http://www.metastudio.org/).
- [https://nroer.gov.in](https://nroer.gov.in/)
- [https://clixoer.tiss.edu](https://clixoer.tiss.edu)

### Features of GNOWSYS

-   A distributed knowledge network.
-   Metadata can also be added to relations and attributes.
-   All changes to the data as well as to the metadata of knowledge is
    tracked.
-   Methods are accessible to clients and other servers as web services
    and through XML-RPC or jsonrpc, as well as restful protocol.
-   Define arbitrary relations and attributes. subtyping, and class
    membership are inbuilt. All the datatypes provided by mongodb are
    supported.
-   Metatype (type of types) and relations among them can also be
    expressed. Useful for knowledge representation using upper ontology
    elements.

### Possible Applications

Consider using GNOWSYS if you want a distributed database, your data
model is evolving (not yet frozen), you are a semantic web engineer and
wants to develop an ontology, or publish several ontologies in one
networked memory, you want a distributed triple store with frame and
graph based views, if you are doing structured content management
application, etc.

You may use GNOWSYS:

-   As a web based hybrid database (as a file system, RDBMS, OODBMS,
    distributed DBMS) with querying and remote management. This ability
    will make it highly suitable for agent oriented computing solutions
    across the Internet.
-   For building structured knowledge bases with a higher degree of
    expressiveness. This will help build AI based applications using
    GNOWSYS as a database. (GNOWSYS has no inbuilt inference engine
    (Ongoing work). However it is possible through the SPARQL endpoint
    provided by [4store](http://4store.org/).
-   For semantic web. All data stored can be exported as RDF (N3
    notation completed), and can be imported from RDF (Ongoing work).
-   Since GNOWSYS database is available as a web-server, dynamic web
    sites and web services can be made. Web sites built with GNOWSYS are
    \"semantic web ready\", for the structure of the data can be queried
    by software agents. Normal dynamic web sites conceal the database
    structure, while GNOWSYS sites do not.
-   Any web framework can make use of the data stored in the GNOWSYS
    knowledge base though XML-RPC/jsonrpc.
-   As a digital encyclopedia, thesaurus, dictionary or glossaries can
    be made very easily.
-   For building elearning applications. Lessons and concepts
    (learning resources) can be organized according to the standard
    metadata suggested by LOM/SCORM models. Learning paths, evaluation
    tracks, usage history etc. can be persistantly stored and accessed
    by establishing networking relations and conditions among
    them. [SELF Platform](http://www.selfplatform.eu/) was our first
    implementation. Latest implementations are
    [http://www.metaStudio.org](http://www.metastudio.org/), [https://nroer.gov.in](https://nroer.gov.in/), and [https://clixoer.tiss.edu](https://clixoer.tiss.edu).

### License

GNOWSYS is free software; you can redistribute it and/or modify it under
the terms of the [Affero GNU General Public
License](http://www.gnu.org/licenses/agpl.html) as published by the Free
Software Foundation; version 3 of the License, or (at your option) any
later version.

GNOWSYS is conceived and authored by Nagarjuna G. Most of the code to
GNOWSYS was a contribution by several staff members and students who
worked under his guidance at Homi Bhabha Centre for Science Education,
TIFR, Mumbai. Shashank Ashtikar and Harshad Bahere were the initial
contributors to the code and later on by Prasanta Baruah, Debarshi Ray
and Rakesh Pandit. Bipin Apandkar, Rajiv Nair, Alpesh Gajbe, Dinesh
Joshi, Vihan Pandey, Saurabh Shelar, Krishnakant Mane, Shaswat
Chakravorty, Divya, Jay Mehta, Kabir, Johnson, Anuja, Supriya, and
Ganesh Gajre, Anuja, Supriya, Dhiru, Krishna,
Avadoot, Johnson, Arun, Kedar, Rachana, Sunny, Kabir and Amit.

The current active contributors include Siddhu, Mahesh, Surendra and
Amit and some student interns of the [gnowledge
lab.](https://www.gnowledge.org/)

GNOWSYS development is currently supported by Homi Bhabha Centre for
Science Education (HBCSE), TIFR, and is mostly executed by undergraduate
students as a part of their projects. Please remember that GNOWSYS is a
GNU project and is dedicated to the free software community. If you like
to be a volunteer, you can also contribute to its development. This
project is managed from savannah site. You can place a request to be a
developer from there. For information about contributing to other GNU
Projects, please read How to help GNU.

### A GNU Project

GNOWSYS is an official GNU project since December 2004. Its development
is currently supported by the [gnowledge lab
of](http://lab.gnowledge.org/) [HBCSE](http://www.hbcse.tifr.res.in/),
[TIFR.](http://www.tifr.res.in/)


