### Optimisitc Concurrency Control

> **Optimistic Concurrency Control** assumes that multiple transactions **can frequently complete without interfering** with each other. While running, transactions use data resources without acquiring locks on those resources. Before committing, each transaction **verifies that no other transaction has modified the data** it has read. If the check reveals conflicting modifications, the committing transaction rolls back and can be restarted... [Read on Wikipedia](https://en.wikipedia.org/wiki/Optimistic_concurrency_control)

#### Phases of OCC
The transactions proceed in OCC in three phases

##### Working phase
- The transaction uses a **tentative version** of the objects it accesses. (dirty reads can’t occur as we read from a committed version or a copy of it)
- The coordinator records the readset and writeset of each transaction.

##### Validation phase
- At closeTransaction the coordinator validates the transaction (looks for conflicts)
- if the validation is successful the transaction can commit.
- if it fails, either the current transaction, or one it conflicts with is aborted

##### Update phase
- If validated, the **changes** in its tentative versions are **made permanent.**
- **Read-only** transactions can **commit immediately** after passing validation.

#### Timestamp ordering concurrency control

##### Each operation in a transaction is validated when it is carried out
-  if an operation cannot be validated, the transaction is aborted
-  each transaction is given a unique timestamp when it starts.
- The timestamp defines its position in the time sequence of transactions.
-  requests from transactions can be totally ordered by their timestamps.

##### Basic Timestamp Ordering rule
- A request to write an object is valid only if that object was last read and written by earlier transactions.
- A request to read an object is valid only if that object was last written by an earlier transaction
