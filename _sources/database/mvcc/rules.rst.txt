MVCC Rules
===============

From a performance point of view, readers should never block writers, and writers should never block readers.
With this principle, database can handle long-running read queries at the same time as processing writes normally, without any lock contention between the two.

Rules
---------------

1. At the start of each transaction, the database makes a list of all the other transactions that are in progress at that time. Any writes that those transactions have made are ignored, even if the transactions subsequently commit.
2. Any writes made by aborted transacations are ignored.
3. Any writes make by transacations with a later transacation ID(i.e., which started after the current transacation started) are ignored, regardless of whether those transacations have commited.
4. All other writes are visible to the application's queries.
 
