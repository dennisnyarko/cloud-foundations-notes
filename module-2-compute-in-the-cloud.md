# Amazon Elastic Compute Cloud (EC2)
- Compute refers to the processing power needed to run applications, manage data, and perform calculations.
- Compute in the cloud means creating virtual machines with a cloud provider to run applications and tasks over the internet.
- They are VMs
Multi-tenancy: allows multiple virtual machines to share resources on the same physical host, with isolation between them.

## Amazon EC2
- on-demand compute capacity that can be quickly launched, scaled, and terminated, with costs based only on active usage.
- Flexible, cost-effective, and faster than managing on-premises servers.

## How EC2 Works
1) Launch the instance: start by selecting (Amazon Machine Image (AMI), which defines the operating system)
2) Connect to the instance: SSH for Linux instances or Remote Desktop Protocol (RDP) for Windows instances. Also AWS Systems Manager offers secure & simplified method for accessing instances.
3) Use: run commands, install software, add storage, organize files, and perform other tasks.

## Amazon EC2 Instance Types
- General purpose: balanced mix of compute, memory, and networking resources.
- Compute optimized: ideal for compute-intensive tasks (gaming servers, high performance computing (HPC), ML, and scientific modeling.
- Memory optimized: for memory-intensive tasks like processing large datasets, data analytics, and databases.
- Accelerated computing: using hardware accelerators, like graphics processing units (GPUs), to efficiently handle tasks, eg. floating-point calculations, graphics processing, and machine learning.
- Storage optimized: for workloads that require high performance for locally stored data, eg. large databases, data warehousing, and I/O-intensive applications.

## How to Provision AWS Resources
You interact with AWS services through API calls
API: an application programming interface that defines predetermined ways for you to interact with AWS services.
### Ways to call/invoke AWS APIs:
- AWS Management Console: point-and-click style (web interface)
- AWS Command Line Interface (CLI): run commands using AWS CloudShell (a cloud-based terminal with the AWS CLI already installed in a managed environment).
- AWS Software Development Kit (SDK): using programming languages (Python)
