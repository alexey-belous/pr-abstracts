# Data Models and Query Languages

## SQL

## NoSQL

Hierarchial NoSQL has many-to-many problem. Debates to solve that were between **network model** and **structured model**

### Network model
```The CODASYL model was a generalization of the hierarchical model```

Node can have multiple parent nodes. Implementation was done as "links". Main problem - complex and inflexible queries, lot of changes of queries are needed if the "access path" is changed.


The main arguments in favor of the **document data model** are 
- schema flexibility
- better performance due to locality
- for some applications it is closer to the data structures used by the application. 

The **relational model** counters by providing better support for 
- joins
- many-to-one 
- many-to-many relationships.

### Document DB:
- Schema on read (aka schemaless)
- items in the collection don’t all have the same structure 
- locality of the data (whole document stored in one place)
- hard rewrites for big documents because document rewritten completely on update

### SQL DB:
- Schema on write
- indexes for joints, more read operations
- but there're options for data locality in SQL solutions

### MapReduce
MongoDB example: 
```
Map for every record of collection -> map emit key and mapped entity -> entities grouped by key -> reduce is called for each group
```

```
NOTE: A usability problem with MapReduce is that you have to write two carefully coordi‐
nated JavaScript functions, which is often harder than writing a single query. More‐
over, a declarative query language offers more opportunities for a query optimizer to
improve the performance of a query.
```

### Graph-Like Data Models
Modeling data as a graph. Vertices and edges.

Tooling:
- Property Graphs (implemented by Neo4j, Titan, and InfiniteGraph)
- Triple-store (Datomic, AllegroGraph, and others)
- Declarative query language (Cypher, SPARQL, and Datalog)
- Imperative query language (Gremlin)
- Graph processing frameworks like Pregel

#### Property Graphs
Each vertex consists of:
- A unique identifier
- A set of outgoing edges
- A set of incoming edges
- A collection of properties (key-value pairs)
  
Each edge consists of:
- A unique identifier
- The vertex at which the edge starts (the tail vertex)
The vertex at which the edge ends (the head vertex)
- A label to describe the kind of relationship between the two vertices
- A collection of properties (key-value pairs)


#### The Cypher Query Language
Cypher is a declarative query language for property graphs, created for the Neo4j
graph database

Alternative of Cypher in SQL is `WITH RECURSIVE` syntax, that is very clumsy.

#### Triple-Stores and SPARQL
In a triple-store, all information is stored in the form of very simple three-part statements: (subject, predicate, object).
```
(Jim, likes, bananas)
Jim is the subject, likes is the predicate (verb), and bananas is the object.
```

#### The Foundation: Datalog
Datalog is used in a few data systems: for example, it is the query language of Datomic, and Cascalog is a Datalog implementation for querying large datasets in Hadoop

```js
// Datalog facts:
name(namerica, 'North America').
type(namerica, continent).
name(usa, 'United States').
type(usa, country).
within(usa, namerica).
```


### Summary
Historically, data started out being represented as one big tree (the hierarchical
model), but that wasn’t good for representing many-to-many relationships, so the
relational model was invented to solve that problem. More recently, developers found
that some applications don’t fit well in the relational model either. New nonrelational
“NoSQL” datastores have diverged in two main directions:
1. Document databases target use cases where data comes in self-contained docu‐
ments and relationships between one document and another are rare.
2. Graph databases go in the opposite direction, targeting use cases where anything
is potentially related to everything
