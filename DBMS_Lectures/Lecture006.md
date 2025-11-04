# Relational Model Introduction

# Data model
1. E-R Model
2. Relation model

now let's talk about relational model

## Relational model
The relational model uses a collection of tables to represent both data and the relationships among those data
![alt text](image-11.png)

## Attribute or field
* Attributes are used to describe relations or columns are attributes
* e.g. id, name, size, type, price, fit in the shirt table


## Tuple or Record
A row in a relation

## Instance
Snapshot of the data in the database at a given instant in time

## Database Schema
Logical design of database  
e.g. Relation_name(attribute1, attribute2, ...)  
account(account_number, branch_name, balance)  
branch(branch_name, branch_address)  
employee(e_id, e_name, e_mail, e_address)  

## Domain
* A unique set of values permitted for an attribute

## Domain Constraint
* Specifies an important condition that we want each instance of relation to satisfy

## Degree or Arity
* Number of attributes in relation

## Cardinality
* Number of tuples in a relation

## Relational Database
* A relational database is a collection of relations
* NULL - representation of no value.
  * We can't put empty, else it will have the garbage value

## Keys
An attribute or set of attributes whose values can uniquely identify a tuple in a relation.

## Types of Keys
1. Super Key
   * All possible keys of a relation
2. Candidate Key
   * Minimal super key
   * A keys whose proper subset is not a key
3. Primary Key
   * Chosen candidate key for implementation
4. Alternate Key
   * All candidate keys apart from primary key
5. Foreign Key
   * It follows the referential integrity constraint
   * Foreign key can be NULL

## Referential Integrity
We wish to ensure that a value that appears in one relation for a given set of attributes also appears for a certain set of attributes in another relation. This condition is called referential integrity.

