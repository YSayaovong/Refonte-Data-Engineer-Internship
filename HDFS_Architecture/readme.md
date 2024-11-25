# HDFS Architecture Simulation

This project simulates a simplified Hadoop Distributed File System (HDFS) architecture. It demonstrates the key concepts of data storage, replication, and retrieval in an HDFS-like environment using Python.

## Key Features

1. **Data Blocks Definition**:
   - Transactions are defined as discrete data blocks.
   - Example data blocks include:
     - `Transaction 1: Deposit $100`
     - `Transaction 2: Withdraw $50`
     - `Transaction 3: Transfer $200`
     - `Transaction 4: Deposit $300`
     - `Transaction 5: Withdraw $100`

2. **Data Node Simulation**:
   - Simulates three data nodes:
     - `DataNode 1`
     - `DataNode 2`
     - `DataNode 3`

3. **Block Distribution**:
   - Randomly distributes the data blocks across the data nodes.
   - Ensures balanced storage across the nodes to mimic HDFS functionality.

4. **Data Replication**:
   - Implements replication to enhance fault tolerance.
   - A replication factor of 2 ensures that each data block is stored in at least two nodes.
   - Avoids duplicate replication by ensuring that a block is not added to the same data node multiple times.

5. **Data Retrieval**:
   - Implements a `retrieve_transaction()` function that locates a specific transaction across all data nodes.
   - Returns the data node where the transaction is found or a message indicating that the transaction is not present.

## Accomplishments

- **Simulated Data Distribution**:
  - Successfully distributed the data blocks across three data nodes.
  - Mimicked the randomness and distribution logic of an HDFS environment.

- **Implemented Replication**:
  - Ensured redundancy by replicating data blocks across multiple nodes.
  - Demonstrated replication logic while avoiding unnecessary duplication.

- **Developed Data Retrieval Logic**:
  - Created a function to locate specific data blocks across nodes.
  - Verified functionality with test cases, including valid and invalid transaction queries.

## Example Output

### Distributed Data
```plaintext
Distributed data:
DataNode 1: ['Transaction 2: Withdraw $50']
DataNode 2: ['Transaction 3: Transfer $200', 'Transaction 5: Withdraw $100']
DataNode 3: ['Transaction 1: Deposit $100', 'Transaction 4: Deposit $300']
