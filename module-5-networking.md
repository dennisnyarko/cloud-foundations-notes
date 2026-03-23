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

3) ### AWS PrivateLink:
This is a highly available, scalable technology that you can use to privately connect your VPC to services and resources as if they were in your VPC. You do not need to use an internet gateway, NAT device, public IP address, Direct Connect connection, or AWS Site-to-Site VPN connection to allow communication with AWS services or resources from your private subnets. Instead, you control the specific API endpoints, sites, services, and resources that are reachable from your VPC.

**Benefits**: AWS PrivateLink helps you secure your traffic and connect with simplified management rules.

**Use case**: It is used for connecting your clients in your VPC to resources, other VPCs, and endpoints.

4) ### AWS Direct Connect:
This service enables you to establish a dedicated private connection between your network and a VPC in the AWS Cloud.

**Benefits**: AWS Direct Connect reduces network costs and increases the amount of bandwidth.


**(to-do: find the exact difference between the four)**

### More about Direct Connect:

- Latency-sensitive applications: Direct Connect bypasses the internet and provides a consistent, low-latency network experience. This makes it ideal for applications like video streaming and other real-time applications that require high performance.
eg: Media files moving quickly labelled latency-sensitive applications.

- Large-scale data migration or transfer: Direct Connect helps ensure smooth and reliable data transfers at massive scale for real-time analysis, rapid data backup, or broadcast media processing.

- Hybrid cloud architecture: You can use Direct Connect to link your AWS and on-premises networks to build applications that span environments without compromising performance.


Here’s a **simple real-world way to understand them**:

---

### 🏠 Scenario: Your company uses AWS

#### 🔹 AWS Client VPN

* Your employee is at home.
* They open their laptop and connect to AWS.
* 👉 Like logging into the company network remotely.

---

#### 🔹 AWS Site-to-Site VPN

* Your company office network connects to AWS.
* Everyone in the office automatically accesses AWS resources.
* 👉 No need for individual VPN logins.

---

#### 🔹 AWS PrivateLink

* Your app in AWS needs to talk to another AWS service (or SaaS).
* It does this **privately without internet exposure**.
* 👉 Like a private internal connection between services.

---

#### 🔹 AWS Direct Connect

* Your company pays for a **dedicated fiber connection** to AWS.
* Faster, more reliable, no internet involved.
* 👉 Like having a private highway to AWS.

---

### ⚡ One-line summary

* **Client VPN** → Remote users
* **Site-to-Site VPN** → Office network
* **PrivateLink** → Private service access
* **Direct Connect** → Dedicated physical connection

---

## Additional gateway services
There are several different types of gateways you can use to connect your AWS resources

- AWS Transit Gateway is used to connect your Amazon VPCs and on-premises networks through a central hub.
- Network Address Translation (NAT) Gateway: You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services can't initiate a connection with those instances.


### Extra points to note

---

### 🔑 What “Gateway” means (simple)

A **gateway** = a resource that **routes traffic between two different networks or systems**.

---

### 🔹 Common AWS Gateway Services (relevant here)

#### 1. Internet Gateway (IGW)

* Connects your VPC to the internet
* Used for public access (web servers, etc.)

👉 VPC ↔ Internet

---

#### 2. Virtual Private Gateway (VGW)

* Used with **Site-to-Site VPN**
* AWS side of the VPN connection

👉 On-prem network ↔ AWS (via VPN)

---

#### 3. Transit Gateway (TGW)

* Central hub to connect **multiple VPCs and on-prem networks**
* Simplifies complex networking

👉 Many VPCs + networks ↔ one central gateway

---

#### 4. NAT Gateway

* Allows private resources to access the internet **without being exposed**

👉 Private subnet → Internet (outbound only)

---

#### 5. VPC Endpoint (Gateway Endpoint & Interface Endpoint)

* Used with **PrivateLink**
* Lets you access AWS services privately

👉 VPC ↔ AWS service (no internet)

---

### 🧠 How it ties to the above topics

* **Site-to-Site VPN** → uses **Virtual Private Gateway**
* **Client VPN** → connects users into VPC (via endpoint, not IGW)
* **PrivateLink** → uses **VPC Endpoints**
* **Direct Connect** → uses **Direct Connect Gateway**

---

### ⚡ Easy way to remember

* **Gateways = traffic controllers**
* They decide **how traffic enters, leaves, or moves within AWS**

---

# Subnets, Security Groups, and Network Access Control Lists

Packets are checked against a Network ACL (Access Control List) to see if the packet has permissions to either ​leave or enter the subnet, based on who it was sent from ​and how it's trying to communicate

Every EC2 instance, when launched, automatically has a security group. ​And by default, the security group does not allow any traffic ​into the instance at all. ​All ports are blocked. ​All IP addresses sending packets are blocked. 

The key difference between a security group and a network ​ACL is that the security group is stateful. ​That means, as we discussed, it has some kind of memory about who to allow in or out. ​And the network ACL is stateless, which remembers nothing and checks ​every single packet that crosses its border, regardless ​of any circumstances

Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound.

Security groups perform stateful packet filtering. They remember previous decisions made for incoming packets.

Network ACL => subnet level security

Security group => instance level security

## Subnets

A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private.

Public subnets contain resources that need to be accessible by the public, such as an online store’s website.

Private subnets contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories.

---
### Network traffic in a VPC (The movement of data packets travelling across a network)

<img width="1530" height="440" alt="image" src="https://github.com/user-attachments/assets/8fe4c01e-5b82-4168-bd10-a59343e0c478" />
---

# Global Networking
- Edge networking is the process of bringing information storage and computing abilities closer to the devices that produce that information and the users who consume it

### AWS Edge Services
- Amazon Route 53 is a DNS that provides a reliable and cost-effective way to route end users to internet applications.
- Amazon CloudFront is a content delivery network (CDN) service that delivers your content with faster loading times, cost savings, and reliability.
- AWS Global Accelerator is a service that uses the AWS global network to improve application availability, performance, and security. It uses intelligent traffic routing and fast failover if something goes wrong in one of your application locations.

---
To learn more, review each of the following numbered items below the image.

<img width="1544" height="674" alt="image" src="https://github.com/user-attachments/assets/a0cf7ea9-29e4-428c-bb0d-0497b5a795ec" />

1) Customer request: A customer requests data from the application by going to AnyCompany’s website.

2) Amazon Route 53: Amazon Route 53 uses DNS resolution to identify AnyCompany.com’s corresponding IP address, 192.0.2.0. This information is sent back to the customer.

3) CloudFront: The customer’s request is sent to the nearest edge location through CloudFront.

4) Application Load Balancer: Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an Amazon EC2 instance.
