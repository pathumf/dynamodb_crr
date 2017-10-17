# dynamodb_crr
implement dynamodb cross region replication

This project aims to provide a serverless solution for replicating DynamoDB table data across regions in near real time. This is achieved through the use of AWS Lambda and DynamoDB Table streams.

# What is a DynamoDB cross-region replication?

DynamoDB cross-region replication allows you to maintain identical copies (called replicas) of a DynamoDB table (called master table) in one or more AWS regions. After you enable cross-region replication for a table, identical copies of the table are created in other AWS regions. Writes to the table will be automatically propagated to all replicas.

# When should I use cross-region replication?

You can use cross-region replication for the following scenarios.

Efficient disaster recovery:`By replicating tables in multiple data centers, you can switch over to using DynamoDB tables from another region in case a data center failure occurs.`

Faster reads: `If you have customers in multiple regions, you can deliver data faster by reading a DynamoDB table from the closest AWS data center.`

Easier traffic management:` You can use replicas to distribute the read workload across tables and thereby consume less read capacity in the master table.`

Easy regional migration: `By creating a read replica in a new region and then promoting the replica to be a master, you migrate your application to that region more easily.`

Live data migration: `To move a DynamoDB table from one region to another, you can create a replica of the table from the source region in the destination region. When the tables are in sync, you can switch your application to write to the destination region.`

# How to setup cross-region replication?
 
Create lambda function or install cross-region replication tool on EC2.

Enable data stream on existing DynamoDB table.

Create target DynamoDB table in another region.

Run and monitor your lambda function or replication tool continuously.
