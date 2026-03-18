# Introduction to Networking
Networking refers to the interconnection of devices that can exchange data and resources. Networking in the AWS Cloud consists of the infrastructure and services working together to host your applications, data, and any other resources you might need.

## Networking Components:
### Amazon Virtual Private Cloud (VPC)
- It is a service from AWS that lets you create a private, isolated network in the cloud where you can run AWS resources (like servers, databases, etc.).
- Amazon VPC lets you design your own network in the cloud with full control over IP addresses, subnets, routing, and security.

**Key Idea** => A VPC = your own virtual data center network inside AWS, where you control IP ranges, subnets, routing, and security.

### Benefits of VPC
- Helps increase security because you can secure and monitor connections, screen traffic, and restrict instance access.
- Gives you full control over your resource placement, connectivity, and security.
- You will spend less time setting up, managing, and validating your virtual network when compared to on-premises network management.

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


So, if you want to establish an encrypted VPN connection to your private internal AWS resources, you need to attach a virtual private gateway to your VPC.


- Amazon Virtual Private Cloud: is used to establish boundaries around your AWS resources.
- Virtual private gateway: allows protected internet traffic to enter into the VPC.
- Virtual private network: A VPN encrypts your internet traffic, helping protect it from anyone who might try to intercept or monitor it.

    - A virtual private gateway + a VPN connection + a private subnet in the Amazon VPC = direct connection to your data center through the internet with a secure connection.
    - AWS Direct Connect lets you establish a completely private, dedicated fibre connection from your data center to AWS.


# More Ways to Connect to the AWS Cloud
Four ways to connect to the AWS Cloud:
1) ### AWS Client VPN: 
This is a networking service you can use to connect your remote workers and on-premises networks to the cloud. It is a fully managed, elastic VPN service that automatically scales up or down based on user demand. Because it is a cloud VPN solution, you don’t need to install and manage hardware or try to estimate how many remote users to support at one time.

**Benefits**: AWS Client VPN provides advanced authentication and remote access. It is elastic and fully managed.

**Use case**: It can be used to quickly scale remote-worker access.

2) ### AWS Site-to-Site VPN: 
This is a highly available, scalable technology that you can use to privately connect your VPC to services and resources as if they were in your VPC. You do not need to use an internet gateway, NAT device, public IP address, Direct Connect connection, or AWS Site-to-Site VPN connection to allow communication with AWS services or resources from your private subnets. Instead, you control the specific API endpoints, sites, services, and resources that are reachable from your VPC.

**Benefits**: AWS PrivateLink helps you secure your traffic and connect with simplified management rules.

**Use case**: It is used for connecting your clients in your VPC to resources, other VPCs, and endpoints.

3) AWS PrivateLink:
This is a highly available, scalable technology that you can use to privately connect your VPC to services and resources as if they were in your VPC. You do not need to use an internet gateway, NAT device, public IP address, Direct Connect connection, or AWS Site-to-Site VPN connection to allow communication with AWS services or resources from your private subnets. Instead, you control the specific API endpoints, sites, services, and resources that are reachable from your VPC.

**Benefits**: AWS PrivateLink helps you secure your traffic and connect with simplified management rules.

**Use case**: It is used for connecting your clients in your VPC to resources, other VPCs, and endpoints.

4) AWS Direct Connect:
This service enables you to establish a dedicated private connection between your network and a VPC in the AWS Cloud.

**Benefits**: AWS Direct Connect reduces network costs and increases the amount of bandwidth.


### More about Direct Connect:

- Latency-sensitive applications: Direct Connect bypasses the internet and provides a consistent, low-latency network experience. This makes it ideal for applications like video streaming and other real-time applications that require high performance.
eg: Media files moving quickly labelled latency-sensitive applications.

- Large-scale data migration or transfer: Direct Connect helps ensure smooth and reliable data transfers at massive scale for real-time analysis, rapid data backup, or broadcast media processing.

- Hybrid cloud architecture: You can use Direct Connect to link your AWS and on-premises networks to build applications that span environments without compromising performance.
