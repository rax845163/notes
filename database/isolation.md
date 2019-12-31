# Isolation
Isolation determines how transaction integrity is visible to other users and systems. Isolation is typically defined at database level as a property that defines how/when the changes made by one operation become visible to other. 

## Isolation levels
* READ UNCOMMITTED
* READ COMMITTED: 
* REPEATABLE READ: In this isolation level, a lock-based concurrency control DBMS implementation keeps read and write locks until the end of the transaction. However, range-locks are not managed, so phantom reads can occur.
* SERIALIZABLE: With a lock-based concurrency control DBMS implementation, serializability requires read and write locks (acquired on selected data) to be released at the end of the transaction. Also range-locks must be acquired

## Cocurrency controll

## Read phenomena
* Dirty reads: A dirty read (aka uncommitted dependency) occurs when a transaction is allowed to read data from a row that has been modified by another running transaction and not yet committed.
* Non-repeatable reads: A non-repeatable read occurs, when during the course of a transaction, a row is retrieved twice and the values within the row differ between reads.
* Phantom reads: A phantom read occurs when, in the course of a transaction, new rows are added or removed by another transaction to the records being read.