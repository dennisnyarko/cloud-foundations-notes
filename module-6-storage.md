# Introduction to Storage
Three types of storage
- Block storage: provides persistent, low-latency block-level storage volumes that attach to EC2 instances like physical hard drives. Block storage volumes can be encrypted, backed up via snapshots, and modified while in use without disrupting the instance. AWS offers two primary block storage services:

  - Amazon EC2 instance store: An unmanaged, non-persistent, high-performance block storage directly attached to EC2 instances for temporary data.

  - Amazon Elastic Block Store (EBS): A managed service that provides persistent block storage volumes for EC2 instances, offering various types for different workloads

- Object storage: It is a data storage architecture that manages data as objects in a flat address space. It offers unlimited scalability so you can store vast amounts of unstructured data without worrying about capacity constraints. It also provides enhanced metadata capabilities to provide more efficient data management, search, and analytics across massive datasets. The following is the primary AWS object storage service:

  - Amazon Simple Storage Service (S3): A fully managed, scalable object storage service for storing and retrieving any amount of data from anywhere.

- File storage: AWS file storage services provide shared file systems accessible over networks, so multiple users and applications can access the same data simultaneously. They offer scalability and flexibility so you can expand storage capacity as needs grow without managing physical infrastructure. AWS offers two primary file storage services:

    - Amazon Elastic File System (EFS):A fully managed, scalable NFS file system for use with AWS Cloud services and on-premises resources.

    - Amazon FSx: A fully managed file storage service for popular file systems like Windows, Lustre, and NetApp ONTAP.

### Additional storage services
These services don't fit cleanly into the categories we've defined so far, but they're important AWS storage offerings that you should be familiar with.

  - AWS Storage Gateway
    A fully managed, hybrid-cloud storage service that provides on-premises access to virtually unlimited cloud storage.

  - AWS Elastic Disaster Recovery
    A fully managed service that streamlines the recovery of your physical, virtual, and cloud-based servers into AWS.

### AWS shared responsibility
AWS Storage Services
The AWS shared responsibility model groups services into three categories based on the ownership of administrative tasks. These categories are fully managed, managed, and unmanaged.
1) **Fully managed services**

   Customer responsibility:
    - Customer data
    - Client-side data encryption

    AWS responsibility:
     - Server-side encryption
     - Network traffic protection
     - Platform and application management
     - OS, network, firewall configuration
     - Software for compute, storage, database, and networking
     - Hardware, AWS global infrastructure
  
2) **Managed services**

   Customer responsibility:
    - Customer data
    - Client-side data encryption
    - Server-side encryption
    - Network traffic protection

    AWS responsibility:
     - Platform and application management
     - OS, network, firewall configuration
     - Software for compute, storage, database, and networking
     - Hardware, AWS global infrastructure

3) **Unmanaged services**

   Customer responsibility:
    - Customer data
    - Client-side data encryption
    - Server-side encryption
    - Network traffic protection
    - Platform and application management
    - OS, network, firewall configuration

    AWS responsibility: 
     - Software for compute, storage, database, and networking
     - Hardware, AWS global infrastructure



