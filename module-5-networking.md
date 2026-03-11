# Introduction to Networking
Networking refers to the interconnection of devices that can exchange data and resources. Networking in the AWS Cloud consists of the infrastructure and services working together to host your applications, data, and any other resources you might need.

## Networking Components:
### Amazon Virtual Private Cloud (VPC)
- It is a service from AWS that lets you create a private, isolated network in the cloud where you can run AWS resources (like servers, databases, etc.).
- Amazon VPC lets you design your own network in the cloud with full control over IP addresses, subnets, routing, and security.

**Key Idea** => A VPC = your own virtual data center network inside AWS where you control IP ranges, subnets, routing, and security.


### Subnet
- It is a smaller network created within a VPC to organize and manage resources in AWS. They are essentially segments of your VPC, allowing you to divide your VPC into smaller, manageable sections. A subnet is a range of IP addresses in your VPC.
    - Types:
         1) Public subnet: resources can communicate with the internet through an Internet Gateway
         2) Private subnet: resources do not have direct access to the internet.

- A VPC can contain multiple subnets.
- AWS resources (like servers) are launched inside subnets.

### Architectural diagram
<img width="2914" height="1508" alt="image" src="https://github.com/user-attachments/assets/a8bc9d25-807a-4ea6-a2b8-87646b66df08" />

# Organizing AWS Cloud Resources
