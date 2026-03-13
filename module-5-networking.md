# Introduction to Networking
Networking refers to the interconnection of devices that can exchange data and resources. Networking in the AWS Cloud consists of the infrastructure and services working together to host your applications, data, and any other resources you might need.

## Networking Components:
### Amazon Virtual Private Cloud (VPC)
- It is a service from AWS that lets you create a private, isolated network in the cloud where you can run AWS resources (like servers, databases, etc.).
- Amazon VPC lets you design your own network in the cloud with full control over IP addresses, subnets, routing, and security.

**Key Idea** => A VPC = your own virtual data center network inside AWS, where you control IP ranges, subnets, routing, and security.


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
- Public-facing resources => To allow traffic from the public internet to flow into and out of your VPC, you must attach what is called an internet gateway to your VPC. An internet gateway is like a doorway that is open to the public.
<img width="2910" height="1538" alt="image" src="https://github.com/user-attachments/assets/51eb718a-314a-4fb9-a9da-f66842e1d9c8" />



- Internal private resources => only allows people in if they are coming from an approved network, not the public internet. This private doorway is called a virtual private gateway, and it allows you to create a VPN connection between a private network, like your on-premises data center or internal corporate network to your VPC.
<img width="3024" height="1964" alt="image" src="https://github.com/user-attachments/assets/cd3c9786-cbaa-435a-90aa-e8f41c51052b" />

Scenarios
1) Public traffic = a coffee shop that is accessible to the public (Customers can enter anytime)
2) Private traffic = a coffee shop located inside a private corporate office building. If I want to go get coffee, I have to badge in to verify my identity.
