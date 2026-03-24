# Introduction to Storage
Three types of storage
- Block storage: provides persistent, low-latency block-level storage volumes that attach to EC2 instances like physical hard drives. Block storage volumes can be encrypted, backed up via snapshots, and modified while in use without disrupting the instance. AWS offers two primary block storage services:

  - Amazon EC2 instance store: An unmanaged, non-persistent, high-performance block storage directly attached to EC2 instances for temporary data.

  - Amazon Elastic Block Store (EBS): A managed service that provides persistent block storage volumes for EC2 instances, offering various types for different workloads.

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
---
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

---
# EC2 Instance Store and Amazon Elastic Block Store (Amazon EBS)
## Amazon EC2 instance store
- It is not a stand-alone AWS block storage service but it refers to the block-level storage that is physically attached to the EC2 instance host computer.
- Its data is lost when an instance is stopped or terminated. (best for temporary memory-based storage needs like buffers, caches, and scratch data).
- It is not recommended for applications that require data retention.

Benefits
- Automatically available storage.
- Cost effective.
- High performance.


## Amazon Elastic Block Store (EBS)
- It provides persistent block-level storage volumes for use with Amazon EC2 instances.
- If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.
- EBS volumes act like external hard drives, offering consistent and low-latency performance for workloads like databases and file systems.
- To create an EBS volume, you define the configuration for things like volume size and type.
- Because EBS volumes are for data that needs to persist, it’s important to back up the data (It's recommended that you take incremental backups of EBS volumes by creating Amazon EBS snapshots).
- Some practical use cases of Amazon EBS include database hosting, backup storage for applications, and rapid deployment of development environments using volume snapshots.

Benefits
- Data migration (EBS volumes can be easily migrated between Availability Zones using snapshots. The snapshots provide a simple way to move data across regions or create copies).
- Instance type changes (you can easily attached them to different instance types)
- Disaster recovery (EBS snapshots provide reliable backup solutions that can be restored in different regions during emergencies).
- Cost Optimization.
- Performance tuning.

# Amazon Elastic Block Store (Amazon EBS) Data Lifecycle
Amazon EBS data lifecycle management involves creating, backing up, and deleting volumes and snapshots. This process optimizes storage costs and helps to ensure data protection.

## EBS Snapshots
- EBS snapshots are point-in-time backups of EBS volume.
- They can be used for disaster recovery, data migration, volume resizing, and for creating consistent backups of production workloads.
- They are incremental, so they only save the blocks on the volume that have changed after your most recent snapshot.
- EBS snapshots can be used to create multiple new volumes, and new volumes created from a snapshot are an exact copy of the original volume at the time the snapshot was taken
- napshots of EBS volumes are stored redundantly in multiple Availability Zones using Amazon S3.

### Working with EBS snapshots
In keeping with the AWS shared responsibility model, as the customer, you are responsible for scheduling and managing regular EBS snapshots as part of your backup strategy. This includes monitoring snapshot costs and deleting unnecessary snapshots to avoid excessive charges. You also need to make sure sensitive data within snapshots is encrypted, verify snapshot integrity, and test restoration procedures regularly.

Benefits of EBS Snapshots
- Data protection and recovery
- Operational flexibility
- Cost effective

### Amazon Data Lifecycle Manager
You can automate the creation, retention, and deletion of EBS snapshots using Amazon Data Lifecycle Manager. Amazon Data Lifecycle Manager can schedule snapshots during off-peak hours to minimize performance impact and automatically delete outdated backups to control storage costs. It's particularly valuable for large-scale deployments where manual snapshot management would be time-consuming and error-prone.

Amazon Data Lifecycle Manager Workflow:
- Create an EBS snapshots policy: create an EBS snapshots policy using the Amazon EC2 console, API calls, AWS Command Line Interface (AWS CLI), SDKs, or AWS CloudFormation.
- Select target resource type: choose either an EBS volume or an EC2 instance as the target for the snapshot.
- Exclude volumes: Narrow down the data to be included in the snapshot by choosing options to exclude either the root volume or data volumes.
- Set custom schedules: Automate the creation, retention, and deletion of EBS snapshots by setting up custom schedules.
- Apply additional actions: Before finalizing the policy, you can apply additional actions. These include configuring elements of the snapshots like tags, snapshot archiving, Amazon EBS fast snapshot restore, cross-Region copying, and cross-account sharing.
