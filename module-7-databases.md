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

# Amazon Relational Database Service (Amazon RDS)
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


# Amazon Aurora
- It is a managed relational database designed to help reduce unnecessary I/O operations and is compatible with MySQL and PostgreSQL.
- It provides high performance and availability, and automatically scales alongside your workloads.
- It replicates data across multiple Availability Zones for enhanced durability and fault tolerance, and features automated backups, encryption at rest, and continuous monitoring.
- Use cases: gaming applications, media and content management, and real-time analytics.


Benefits
- High performance and availability: It delivers up to five times the throughput of standard MySQL and three times the throughput of PostgreSQL. It uses a distributed storage system across multiple nodes to provide high performance and availability.
- Automated storage and backup management: It automatically grows storage from 10 GB to 128 TB based on your actual data usage, which eliminates guesswork in capacity planning. It also continuously backs up your database to Amazon S3 to provide point-in-time recovery.
- Advanced replication and fault tolerance: It replicates data across three Availability Zones with six copies of data, and provides 99.99% availability. It automatically detects database failures and redirects traffic to healthy replicas without data loss.

#NoSQL Database Services
