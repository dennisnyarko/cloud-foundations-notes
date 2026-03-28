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
- It is not a stand-alone AWS block storage service, but it refers to the block-level storage that is physically attached to the EC2 instance host computer.
- Its data is lost when an instance is stopped or terminated. (best for temporary memory-based storage needs like buffers, caches, and scratch data).
- It is not recommended for applications that require data retention.

Benefits
- Automatically available storage.
- Cost-effective.
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
- EBS snapshots can be used to create multiple new volumes, and new volumes created from a snapshot are an exact copy of the original volume at the time the snapshot was taken.
- Snapshots of EBS volumes are stored redundantly in multiple Availability Zones using Amazon S3.

### Working with EBS snapshots
In keeping with the AWS shared responsibility model, as the customer, you are responsible for scheduling and managing regular EBS snapshots as part of your backup strategy. This includes monitoring snapshot costs and deleting unnecessary snapshots to avoid excessive charges. You also need to make sure sensitive data within snapshots is encrypted, verify snapshot integrity, and test restoration procedures regularly.

Benefits of EBS Snapshots
- Data protection and recovery
- Operational flexibility
- Cost-effective

### Amazon Data Lifecycle Manager
You can automate the creation, retention, and deletion of EBS snapshots using Amazon Data Lifecycle Manager. Amazon Data Lifecycle Manager can schedule snapshots during off-peak hours to minimize performance impact and automatically delete outdated backups to control storage costs. It's particularly valuable for large-scale deployments where manual snapshot management would be time-consuming and error-prone.

Amazon Data Lifecycle Manager Workflow:
- Create an EBS snapshots policy: create an EBS snapshots policy using the Amazon EC2 console, API calls, AWS Command Line Interface (AWS CLI), SDKs, or AWS CloudFormation.
- Select target resource type: choose either an EBS volume or an EC2 instance as the target for the snapshot.
- Exclude volumes: Narrow down the data to be included in the snapshot by choosing options to exclude either the root volume or data volumes.
- Set custom schedules: Automate the creation, retention, and deletion of EBS snapshots by setting up custom schedules.
- Apply additional actions: Before finalizing the policy, you can apply additional actions. These include configuring elements of the snapshots like tags, snapshot archiving, Amazon EBS fast snapshot restore, cross-Region copying, and cross-account sharing.
---
# Amazon Simple Storage Service (Amazon S3)
- It is a fully managed, highly available object storage service for storing and retrieving any amount of data as objects.
- It offers 99.999999999 percent durability, meaning your data is highly protected against loss.
- It offers features like versioning, lifecycle management, and various storage classes to optimize costs.
- It stores files as objects in containers known as buckets, and each object can range in size from a few bytes to several terabytes.

### Elements
S3 objects:
- An object in Amazon S3 is the fundamental unit of data storage. When you upload a file to Amazon S3, it becomes an object and is stored durably across multiple facilities within your chosen Region.
- Each object typically includes the data itself, metadata, and a unique identifier, or key.
- Objects can be of any file type, such as images, videos, documents, or application data, and can range in size from a few bytes to several terabytes.
- Each Amazon S3 object is uniquely identified within a bucket by its key, which is essentially its file name.
- Objects also have properties like version ID, access control information, and user-defined metadata.

S3 buckets:
- An S3 bucket is a container for storing objects in Amazon S3.
- Buckets have a globally unique name across all of AWS, which helps to identify and organize your stored data.
- Buckets serve as the basic unit for access control and can hold a virtually unlimited number of objects.
- They play a crucial role in data management by making it possible to group related objects and apply policies at the bucket level.
- When creating a bucket, you specify its name and the Region where it will reside. Buckets can be configured with various settings, including versioning, logging, and access permissions.

Benefits:
- Virtually unlimited storage.
- Object lifecycle management.
- Broad range of use cases (content distribution, hosting static websites, and delivering media files).


### Security and privacy management.

To learn more about Amazon S3 security management features, review each of the following three policies:
- Bucket policies

Amazon S3 bucket policies are resource-based policies that can only be attached to S3 buckets. An S3 bucket policy specifies which actions are allowed or denied on the bucket, in addition to every object in that bucket.

- Identity-based policies

Permissions that control what actions users, groups, or roles can perform on S3 resources are configured using identity-based policies. These policies attach directly to identities rather than to the S3 resources themselves. You can use these policies to specify which S3 buckets and objects users can access and what actions they can perform.

- Encryption

Amazon S3 provides encryption capabilities to protect data both at rest and in transit. These encryption features help maintain data confidentiality and comply with various security standards and regulations. These capabilities are as follows:
    
  1) Encryption at rest secures data stored in S3 buckets, preventing unauthorized access to stored objects.
  2) Encryption in transit safeguards data travelling to and from Amazon S3, maintaining secure communication between clients and the service.

# Amazon S3 Storage Classes and S3 Lifecycle
9 Storage Classes
1) S3 Standard:
    - S3 Standard is considered general-purpose storage for cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics.
    - When you upload an object to Amazon S3 without specifying a storage class, the object is added to S3 Standard by default.
    
2) S3 Intelligent-Tiering:
    - This tier is useful if your data has unknown or changing access patterns.
    - S3 Intelligent-Tiering stores objects in three tiers: a frequent access tier, an infrequent access tier, and an archive instant access tier.
    - Amazon S3 monitors access patterns of your data and automatically moves your data to the most cost-effective storage tier based on frequency of access.
    
3) S3 Standard Infrequent Access (Standard-IA):
    - It is for data that is accessed less frequently but requires rapid access when needed.
    - It offers the high durability, high throughput, and low latency of S3 Standard, with a low per-GiB storage price and per-GiB retrieval fee.
    - This storage tier is ideal if you want to store long-term backups, disaster recovery files, and so on.
    
4) S3 One Zone Infrequent Access (One Zone-IA):
    - It stores data in a single Availability Zone, reducing costs compared to S3 Standard-IA, which uses three zones.
    - This storage class suits customers seeking affordable storage for infrequently accessed data without high availability needs.
    - It's perfect for storing secondary backups or easily recreatable data.
    
5) S3 Express One Zone:
    - It stores data in a single Availability Zone.
    - It was purpose-built to deliver consistent single-digit millisecond data access for your most frequently accessed data and latency-sensitive applications.
    - It delivers data access speed up to 10x faster and request costs up to 80% lower than S3 Standard.
    
6) S3 Glacier Instant Retrieval:
    - It is used for archiving data that is rarely accessed and requires millisecond retrieval.
    - Data stored in this storage class offers a cost savings of up to 68 percent compared to the S3 Standard-IA storage class, with the same latency and throughput performance.
    
7) S3 Glacier Flexible Retrieval:
    - It offers low-cost storage for archived data that is accessed 1–2 times per year.
    - Your data can be accessed in as little as 1–5 minutes using an expedited retrieval.
    - You can also request bulk retrievals in up to 5–12 hours at no additional cost.
    - It's an ideal solution for backup, disaster recovery, offsite data storage needs, and for when some data occasionally must be retrieved in minutes.
    
8) S3 Glacier Deep Archive:
    - It is the lowest-cost Amazon S3 storage class.
    - It supports long-term retention and digital preservation for data that might be accessed once or twice per year.
    - Data stored in the S3 Glacier Deep Archive storage class has a default retrieval time of 12 hours.
    - It is designed for customers who retain data sets for 7–10 years or longer, to meet regulatory compliance requirements. eg. financial services, healthcare, and public sectors.
    
9) S3 Outposts:
    - It delivers object storage to your on-premises AWS Outposts environment using Amazon S3 APIs and features, and serves workloads with local data residency requirements.
    - It also helps maintain optimal performance when data must remain in close proximity to on-premises applications.


## S3 Lifecycle
To avoid manually managing your object storage tier configurations, you can use S3 Lifecycle configurations to automate the process. When you define a lifecycle configuration for an object or group of objects, you can choose to automate between two types of actions, as follows:

  - Transition actions: define when objects should transition to another storage class.
  - Expiration actions: define when objects expire and should be permanently deleted.
---

# Amazon Elastic File System (Amazon EFS)
- It is a fully managed, scalable file storage service for use with AWS cloud services and on-premises resources.
- It operates using the Linux Network File System (NFS) protocol, and automatically scales to petabytes as you add or remove files without disrupting applications.
- EFS is designed to support a wide variety of workloads and can be accessed by multiple EC2 instances simultaneously.

Benefits
- Multi-AZ redundancy.
- Shared Access (multiple EC2 instances can access the same file system simultaneously).
- Elastic Storage.

### Amazon EFS storage classes
3 Storage Classes:
1) Standard Storage Classes

The EFS Standard and EFS Standard-Infrequent Access (Standard-IA) storage classes offer Multi-AZ resilience and the highest levels of durability and availability. They have a higher cost associated with them due to higher availability and durability.

2) One Zone Storage Classes

The EFS One Zone and EFS One Zone-Infrequent Access (EFS One Zone-IA) provide additional savings by saving your data in a single Availability Zone. By using just one Availability Zone, you can reduce your storage costs when compared to the Standard EFS storage classes.

3) Archive Storage Classes

The EFS Archive storage class is cost-optimized for data that is accessed only a few times a year or less and that does not need the sub-millisecond latencies of EFS Standard. EFS Archive offers a storage price up to 50% lower compared to EFS Infrequent Access, providing a more cost-optimized experience for cold, rarely-accessed data.

## Amazon EFS data lifecycle
- Transition to IA

This policy instructs lifecycle management when to move files into the Infrequent Access storage, which is cost-optimized for data that is accessed only a few times each quarter. By default, files that are not accessed in Standard storage for 30 days are transitioned into IA.

- Transition to Archive

This policy instructs lifecycle management when to move files into the Archive storage class, which is cost-optimized for data that is accessed only a few times each year or less. By default, files that are not accessed in Standard storage for 90 days are transitioned into Archive.

- Transition to Standard

This policy instructs lifecycle management whether to transition files out of IA or Archive and back into Standard storage when the files are accessed in the IA or Archive storage. By default, files are not moved back to Standard storage, and they remain in the IA or Archive storage class when they are accessed.

# Amazon FSx
- It makes it convenient and cost-effective to launch, run, and scale feature-rich, high-performance file systems in the cloud.
- It supports a wide range of workloads with its reliability, security, scalability, and broad set of capabilities.
- Compared to Amazon EFS, which focuses on the Network File System (NFS) compatibility, Amazon FSx supports multiple filesystem protocols, including Windows File Server, Lustre, OpenZFS, and NetAPP ONTAP.
- It is built on the latest AWS compute, networking, and disk technologies to provide high performance and lower total cost of ownership (TCO).
- As a fully managed service, it handles hardware provisioning, patching, and backups.

Amazon FSx benefits
- File system integration.
- Managed Infrastructure.
- Scalable Storage
- Cost-effective.
