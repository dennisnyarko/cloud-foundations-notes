# Introduction to Databases
AWS database services include options for:
- Relational databases.
- Nonrelational databases.
- In-memory caches.

# Relational Database Services

## Relational Databases
- They use a rigid schema that organizes collections of data into tables with rows and columns, where relationships exist between different tables.
- They store data in a way that relates it to other pieces of data, and they use structured query language, or SQL, to manage and query data.
- This approach stores data in an easily understandable, consistent, and scalable way that works great for applications requiring structured data management.
- AWS offers fully managed relational database solutions that remove the burden of database administration while maintaining high availability and security.
- AWS relational databases support popular database engines like MySQL, PostgreSQL, and Oracle, making it easier to migrate existing databases to AWS.
- An example of a relational database would be an inventory management system for a restaurant. Each record in the database includes data for a single item, such as product name, size, price, and so on.

## Amazon Relational Database Service (Amazon RDS)
- It is a managed relational database service that handles routine database tasks such as backups, patching, and hardware provisioning.
- It supports multiple database instance class types that optimize for memory, performance, or input/output (I/O).
- Amazon RDS offers Multi-AZ deployment and automated backups, but you can also manually create backups using DB snapshots.
- Amazon RDS offers security features including network isolation, encryption in transit, and encryption at rest.
- Amazon RDS supports different database engines, including Amazon Aurora, MySQL, PostgreSQL, Microsoft SQL Server, MariaDB, and Oracle Database.
- Use cases: web applications, enterprise workloads, and product inventories for e-commerce platforms.


Benefits
- Cost optimization: It eliminates the high upfront costs of purchasing and maintaining database hardware infrastructure.
- Multi-AZ Deployment: It improves database reliability through Multi-AZ deployments. During system failures, maintenance, or zone disruptions, Amazon RDS automatically fails over to the standby instance without manual intervention.
- Performance Optimization: It enhances database performance through automated management of resource allocation, monitoring, and optimization tasks.
- Security Controls: It enhances database security through multiple layers of protection, including VPC isolation as well as encryption at rest and in transit.


## Amazon Aurora
- It is a managed relational database designed to help reduce unnecessary I/O operations and is compatible with MySQL and PostgreSQL.
- It provides high performance and availability, and automatically scales alongside your workloads.
- It replicates data across multiple Availability Zones for enhanced durability and fault tolerance, and features automated backups, encryption at rest, and continuous monitoring.
- Use cases: gaming applications, media and content management, and real-time analytics.


Benefits
- High performance and availability: It delivers up to five times the throughput of standard MySQL and three times the throughput of PostgreSQL. It uses a distributed storage system across multiple nodes to provide high performance and availability.
- Automated storage and backup management: It automatically grows storage from 10 GB to 128 TB based on your actual data usage, which eliminates guesswork in capacity planning. It also continuously backs up your database to Amazon S3 to provide point-in-time recovery.
- Advanced replication and fault tolerance: It replicates data across three Availability Zones with six copies of data, and provides 99.99% availability. It automatically detects database failures and redirects traffic to healthy replicas without data loss.


# NoSQL Database Services

## NoSQL Databases
- It uses flexible data schemas for storing and retrieving many different types of information.
- Sometimes referred to as non-relational databases because their structures are different than relational databases like Amazon RDS.
- Instead of row and column relationships, NoSQL databases build a structure for the data that they contain using key-value pairs instead.
- With key-value pairs, data is organized into items identified by unique keys.


## Amazon DynamoDB
- It is a fully managed NoSQL database service that provides fast and predictable performance for both document and key-value data structures.
- Fast option for cases that require a flexible schema, and applications that require high performance and seamless scaling.
- It automatically spreads your data across multiple servers to handle your workload.
- Use cases: gaming platforms, financial service applications, and mobile applications with global user bases.

Benefits
- Scalability with provisioned capacity: It automatically scales throughput up or down based on actual usage, which ensures consistent performance without manual intervention.
- Consistent high performance: It delivers single-digit millisecond response times at any scale, which makes it ideal for high-performance applications.
- High availability and durability: It delivers 99.999% data availability by replicating data across three distinct facilities within each AWS Region. (to provide built-in fault tolerance and data durability).
- Data encryption: It offers comprehensive encryption capabilities to protect information both at rest and in transit.

# In-Memory Caching Services

## In-memory caches
- It is a high-speed storage layer that temporarily stores frequently accessed data in a computer's main memory, or RAM.
- Ideal for storing session data, API responses, database query results, and other information that applications require repeatedly.


NB: When applications need specific information, they first check the cache before requesting it from the original data source. This reduces the load on primary databases and speeds up response times for end users.

## Amazon ElastiCache
- It is a fully managed in-memory caching service that was built to help reduce the complexity of administering in-memory caching systems.
- It automatically detects and replaces failed nodes, which makes it ideal for applications that need consistent high performance.
- Use cases: session data management, database query enhancement, and gaming leaderboards.

Benefits:
- High performance for Redis, Valkey or Memcached instances: It streamlines the deployment and maintenance of in-memory caching environments, offering high availability for Redis, Valkey, and Memcached by automatically handling hardware provisioning, software patching, and monitoring.
- High availability: It provides high availability by constantly monitoring primary nodes for potential failures. When issues are detected, it maintains application availability while promoting a replica node to become the new primary without manual intervention. (all done in minutes)
- Replication across multiple Availability Zones: It enables automatic replication across multiple Availability Zones to protect against infrastructure failures.
- Data encryption: It supports data encryption mechanisms to safeguard sensitive information throughout its lifecycle.

# Additional Database Services
## Amazon DocumentDB
- It is fully managed service designed to handle semistructured data, which is information that doesn't conform to rigid relational schemas.
- It is a MongoDB-compatible database, so it manages JSON-like documents with dynamic schemas.
- Perfect for applications requiring frequent schema changes and document-oriented data.
- Use cases: content management systems, catalog and inventory management, and user profile and personalization systems.

Benefits:
- MongoDB compatibility
- Performance and scalability: automatically scales storage up to 64 TB in 10 GB increments based on your application needs.
- Increased read throughput: by creating up to 15 replica instances that share underlying storage.


## AWS Backup
- It streamlines data protection across various AWS resources and on-premises deployments by providing a single dashboard for monitoring and managing backups.
- It eliminates the complexity of managing multiple backup strategies by supporting multiple storage types, including Amazon Elastic Block Store (Amazon EBS) volumes, Amazon Elastic File System (Amazon EFS) file systems, and various databases.
- 
