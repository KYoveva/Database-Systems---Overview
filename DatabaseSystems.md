# 1. What datatabase models do you know?
* Flat model - consists of a single, two-dimensional array of data elements, where all members of a given column are assumed to be similar values, and all members of a row are assumed to be related to one another. 

* Relational model - In the relational model of a database, all data is represented in terms of tuples, grouped into relations. A database organized in terms of the relational model is a relational database. 

# 2. Which are the main functions performed by a Relational Database Management System (RDBMS)?
* Data Storage Management -This particular function is used for the storage of data and any related data entry forms or screen definitions, report definitions, data validation rules, procedural code, and structures that can handle video and picture formats.

* Data Transformation and Presentation - This function exists to transform any data entered into required data structures.

* Security Management - Security management sets rules that determine specific users that are allowed to access the database.

* Multiuser Access Control - It enables multiple users to access the database simultaneously without affecting the integrity of the database.

* Backup and Recovery Management - Backup and recovery is brought to mind whenever there is potential outside threats to a database. 

* Data Integrity Management 

#  3. Define what is "table" in database terms.
* In relational databases, a table is a set of data elements(values) using a model of vertical columns(identifiable by name) and horizontal rows, the cell being the unit where a row and column intersect. 

# 4. Explain the difference between a primary and a foreign key.
* The columns subset which uniquely identifies a row is called the primary key.

* A foreign key (FK) is a column or combination of columns that is used to establish and enforce a link between the data in two tables to control the data that can be stored in the foreign key table. 

# 5. Explain the different kinds of relationships between tables in relational databases.
* One to One Relationships - In a one-to-one relationship, a row in table A can have no more than one matching row in table B, and vice versa. A one-to-one relationship is created if both of the related columns are primary keys or have unique constraints.

* One to Many and Many to One Relationships - A one-to-many relationship is the most common type of relationship. In this type of relationship, a row in table A can have many matching rows in table B, but a row in table B can have only one matching row in table A. 

* Many to Many Relationships - In a many-to-many relationship, a row in table A can have many matching rows in table B, and vice versa. You create such a relationship by defining a third table, called a junction table, whose primary key consists of the foreign keys from both table A and table B.

* Self Referencing Relationships - A self-join is a relationship in which both match fields are defined in the same table

# 6. When is a certain database schema normalized? What are the advantages of normalized databases?
* A typical example of normalization is that an entity's unique ID is stored everywhere in the system but its name is held in only one table. The name can be updated more easily in one row of one table.

* The benefits of normalization include:
  * Searching, sorting, and creating indexes is faster, since tables are narrower, and more rows fit on a data page.
  * You usually have more tables.
  * You can have more clustered indexes (one per table), so you get more flexibility in tuning queries.
  * Index searching is often faster, since indexes tend to be narrower and shorter.
  * More tables allow better use of segments to control physical placement of data.
  * You usually have fewer indexes per table, so data modification commands are faster.
  * Fewer null values and less redundant data, making your database more compact.
  * Triggers execute more quickly if you are not maintaining redundant data.
  * Data modification anomalies are reduced.
  * Normalization is conceptually cleaner and easier to maintain and change as your needs change.
  
# 7. What are database integrity constraints and when are they used?
* Constraints are the rules enforced on data columns on table. These are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the database.
  
# 8. Point out the pros and cons of using indexes in a database.
* The advantages of indexes are as follows:
  * Their use in queries usually results in much better performance.
  * They make it possible to quickly retrieve (fetch) data.
  * They can be used for sorting. A post-fetch-sort operation can be eliminated.
  * Unique indexes guarantee uniquely identifiable records in the database.
* The disadvantages of indexes are as follows:
  * They decrease performance on inserts, updates, and deletes.
  * They take up space (this increases with the number of fields used and the length of the fields).
  * Some databases will monocase values in fields that are indexed.
  
# 9. What's the main purpose of the SQL language?
* Allowing users to access data on an ad hoc basis required giving them a language in which to express their requests. A single request to a database is defined as a query; such a language is called a query language. Many query languages were developed for this purpose, but one of these became the most popular: Structured Query Language.

# 10. What are transactions used for? Give an example.
* A transaction symbolizes a unit of work performed within a database management system (or similar system) against a database, and treated in a coherent and reliable way independent of other transactions. They are used to:
  * provide reliable units of work that allow correct recovery from failures and keep a database consistent even in cases of system failure, when execution stops (completely or partially) and many operations upon a database remain uncompleted, with unclear status.
  * provide isolation between programs accessing a database concurrently. If this isolation is not provided, the programs' outcomes are possibly erroneous.
* Example:
DECLARE @TranName VARCHAR(20);
SELECT @TranName = 'MyTransaction';

BEGIN TRANSACTION @TranName;
USE AdventureWorks2012;
DELETE FROM AdventureWorks2012.HumanResources.JobCandidate
    WHERE JobCandidateID = 13;

COMMIT TRANSACTION @TranName;
GO

# 11. What is a NoSQL database?
* A NoSQL (originally referring to "non SQL" or "non relational") database provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases.

# 12. Explain the classical non-relational data models.
* Key-value stores - The key-value model is one of the simplest non-trivial data models, and richer data models are often implemented on top of it. The key-value model can be extended to an ordered model that maintains keys in lexicographic order. This extension is powerful, in that it can efficiently process key ranges.

* Document store - The central concept of a document store is the notion of a "document". While each document-oriented database implementation differs on the details of this definition, in general, they all assume that documents encapsulate and encode data (or information) in some standard formats or encodings. Encodings in use include XML, YAML, and JSON as well as binary forms like BSON. Documents are addressed in the database via a unique key that represents that document. One of the other defining characteristics of a document-oriented database is that in addition to the key lookup performed by a key-value store, the database offers an API or query language that retrieves documents based on their contents 

* Graph - This kind of database is designed for data whose relations are well represented as a graph (elements interconnected with an undetermined number of relations between them). The kind of data could be social relations, public transport links, road maps or network topologies, for example. 

# 13. Give few examples of NoSQL databases and their pros and cons.
* Redis -  is a data structure server. It is open-source, networked, in-memory, and stores keys with optional durability. 

* MongoDB - MongoDB (from humongous) is a cross-platform document-oriented database. Classified as a NoSQL database, MongoDB eschews the traditional table-based relational database structure in favor of JSON-like documents with dynamic schemas (MongoDB calls the format BSON), making the integration of data in certain types of applications easier and faster.
Advantages:
  * Enables horizontal scalability by using a technique called sharding.
  * Provides ACID properties at the document level as in the case of relational databases.
  * It supports replica sets.
  * It supports the common authentication mechanisms, such as LDAP, AD, and certificates. Users can connect to MongoDB over SSL and the data can be encrypted.

* CouchDB - Apache CouchDB, commonly referred to as CouchDB, is an open source database that focuses on ease of use and on being "a database that completely embraces the web". It is a document-oriented NoSQL database that uses JSON to store data, JavaScript as its query language using MapReduce, and HTTP for an API. 
Advantages:
  * Fast and agile schema updates/changes
  * Map Reduce queries in a turing complete language of your choice. (no more sql)
  * Flexible Schema designs
  * Freeform Object Storage
  * Really really easy replication
  * Really Really easy Load-Balancing (soon) 
  
