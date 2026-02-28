# Cloud Computing
- The on-demand delivery of IT resources over the internet with pay-as-you-go pricing

## Cloud deployment types
- Cloud-based: migrate existing resources to the cloud
- On-premises: deploying resources on premises using virtualization and resource management tools (dedicated resources & low latency)
- Hybrid: cloud-based resources and on-premises infrastructure work together. Multi-cloud deployments can also be considered hybrid deployments.

## Benefits of the cloud
- Trade fixed expense for variable expense.
- Benefit from massive economies of scale.
- Stop guessing capacity.
- Increase speed and agility.
- Stop spending money to run and maintain data centers.
- Go global in minutes.

## AWS Global Infrastructure (AWS Regions and Availability Zones)
- AWS Regions: physical locations around the world that contain groups of data centers.
- Availability Zones: one or more data centers with redundant power, networking, and connectivity.
- Each AWS Region consists of a minimum of three physically separate Availability Zones within a geographic area.
- **Benefits**: low-latency (high availability), fault-tolerant access to services for users within a given area.
- Distribute your resources across multiple AZs to keep your business applications running in case an AZ experiences an outage.

## AWS Shared Responsibility Model
- concept designed to help AWS and customers work together to create a secure, functional cloud environment.

## Components of the AWS Shared Responsibility Model
### Customer responsibility (Security IN the cloud):
- managing security requirements for their data.
- managing which data they store on AWS and who has access to that data.
- control how access to the data is granted, managed, and revoked.
- responsible for client-side encryption.
### Customer or AWS Responsibilty (Varies by service):
- Server-side encryption.
- Network traffic protection
- Platform and application management
- OS, network, firewall configuration
### AWS Responsibilty (Security OF the cloud)
- Software for compute, storage, database and networking.
- Hardware, AWS Global Infrastructure.

# BONUS:
## Cloud Service Models

### 1. IaaS (Infrastructure as a Service)
Provides virtual machines, storage, and networking.  
You manage the OS, runtime, and applications.

### 2. PaaS (Platform as a Service)
Provides a platform for building and deploying applications.  
The provider manages infrastructure and OS. You manage your code.

### 3. SaaS (Software as a Service)
Provides fully managed software accessible via browser.  
The provider manages everything. You just use the application.
