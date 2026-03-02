# Amazon Elastic Compute Cloud (EC2)
- Compute refers to the processing power needed to run applications, manage data, and perform calculations.
- Compute in the cloud means creating virtual machines with a cloud provider to run applications and tasks over the internet.
- They are VMs
- Multi-tenancy: allows multiple virtual machines to share resources on the same physical host, with isolation between them.

## Amazon EC2
- On-demand compute capacity that can be quickly launched, scaled, and terminated, with costs based only on active usage.
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

### Bonus: 
- Amazon EC2 is the cloud service that lets you rent virtual computers.
- An EC2 instance is the virtual computer you actually run.

## How to Provision AWS Resources
You interact with AWS services through API calls
API: an application programming interface that defines predetermined ways for you to interact with AWS services.
### Ways to call/invoke AWS APIs:
- AWS Management Console: point-and-click style (web interface)
- AWS Command Line Interface (CLI): run commands using AWS CloudShell (a cloud-based terminal with the AWS CLI already installed in a managed environment).
- AWS Software Development Kit (SDK): using programming languages (Python)

## Launching an Amazon EC2 Instance
1) Configure the AMI to define the operating system and software.
2) Select the instance type to allocate CPU, memory, and storage.
3) Set up storage options, including the type and size of the volume.
- Amazon Machine Images (AMI): pre-built virtual machine images that have the basic components for what is needed to start an instance.
- AMI: includes the operating system, storage setup, architecture type, permissions for launching, and any extra software that is already installed.

## Amazon EC2 Pricing
- On-demand instances: Pay only for the compute capacity you consume with no upfront payments or long-term commitments required.
- Reserved instances: Save up to 75% by committing to a 1-year or 3-year term for predictable workloads.
- Spot instances: Bid on spare compute capacity at up to 90% off the On-Demand price, with the flexibility to be interrupted when AWS reclaims the instance.
- Savings plan: Save up to 72% across a variety of instance types and services by committing to a consistent usage level for 1 or 3 years.
- Dedicated hosts: Reserve an entire physical server for your exclusive use with full control (for security & licensing needs).
- Dedicated instances: Pay for instances running on hardware dedicated solely to your account. (isolated from other AWS customers).
- dedicated host gives you your own physical server while dedicated instance offer isolation but still use shared infrastructure.
- Dedicated Hosts offer exclusive use of a server with full control, whereas Dedicated Instances provide isolation without server control.

## Scaling Amazon EC2
- Scalability: the ability of a system to handle an increased load by adding resources.
- Scale up: adding more power to existing machines.
- Scale out: adding more machines.

- Elasticity: ability to automatically scale resources up or down in response to real-time demand.

### Amazon EC2 Auto Scaling
- automatically adjusting the number of EC2 instances based on changes in application demand, providing better availability.

### EC2 Auto Scaling offers Two approaches:
1) Dynamic scaling: adjusts in real time to fluctuations in demand.
2) Predictive scaling: preemptively schedules the right number of instances based on anticipated demand.

### An Auto Scaling group is configured with the following three key settings:
- Minimum capacity: defines the least number of EC2 instances required to keep the application running.
- Desired capacity: the ideal number of instances needed to handle the current workload, which Auto Scaling aims to maintain.
- Maximum capacity: sets an upper limit on the number of instances that can be launched, preventing over-scaling and controlling costs.

# Elastic Load Balancing (ELB)
- automatically distributes incoming application traffic across multiple resources, such as EC2 instances, to optimize performance and reliability.
- A load balancer serves as the single point of contact for all incoming web traffic to an Auto Scaling group.

### ELB Benefits
1) fficient traffic distribution: evenly distributes traffic across EC2 instances, preventing overload on any single instance and optimizing resource utilization.
2) Automatic scaling: scales with traffic and automatically adjusts to changes in demand for a seamless operation as backend instances are added or removed.
3) Simplified management: decouples front-end and backend tiers and reduces manual synchronization. It also handles maintenance, updates, and failover to ease operational overhead.

### ELB Routing Methods
- Round Robin: Distributes traffic evenly across all available servers in a cyclic manner.
- Least Connections: Routes traffic to the server with the fewest active connections, maintaining a balanced load.
- IP Hash: Uses the client’s IP address to consistently route traffic to the same server.
- Least Response Time: Directs traffic to the server with the fastest response time, minimizing latency.

### NB: 
- ELB and Auto Scaling work together to efficiently manage varying levels of demand. ELB is responsible for distributing incoming traffic evenly across multiple EC2 instances. This makes sure that no single instance becomes overwhelmed. It also serves as a single-entry point for traffic into an Auto Scaling group, directing requests to the appropriate resources.
- Meanwhile, Auto Scaling automatically adjusts the number of EC2 instances based on the demand. It adds or removes instances as needed for optimal performance and resource usage. Together, ELB and Auto Scaling help maintain application reliability and cost efficiency.

# Messaging & Queuing
- Amazon Simple Queue Service (SQS): facilitates reliable communication between software components. An application places messages into a queue, and a user or service retrieves the message, processes it, and then removes it from the queue.
- Amazon Simple Notification Service (SNS): a publish-subscribe service that publishers use to send messages to subscribers through SNS topics.
- Amazon EventBridge: a serverless service that helps connect different parts of an application using events, helping to build scalable, event-driven systems.
  - EventBridge can route events, like order placed or payment completed, to the relevant services (payment, restaurant, inventory, and delivery). It can handle high volumes of events during peak times, making sure each service works independently. Even if one service fails, EventBridge will store the event and process it as soon as the service is available again. EventBridge helps provide a smooth and reliable operation across the entire system.
