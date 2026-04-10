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
