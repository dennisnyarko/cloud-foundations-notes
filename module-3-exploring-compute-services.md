# Introduction to Serverless Computing
- With serverless computing, you run applications without managing the underlying infrastructure
- Unmanaged services: like Amazon EC2, AWS takes care of the underlying physical infrastructure, but you're responsible for setting up, securing, and maintaining the operating system, network configurations, and applications on your instances.
- Managed services: handles most of the infrastructure for you, but you still need to set up things like deployment options, scaling, and environment settings.
- Fully-managed services: (like AWS Lambda), you don’t manage any servers at all. You upload your code, and AWS takes care of the rest, including infrastructure, scaling, and availability.

## AWS Lambda
- Lambda is a serverless compute service that runs code in response to events without the need to provision or manage servers.
- It automatically manages the underlying infrastructure, scaling resources based on the volume of requests.
- You are charged only for the compute time consumed, down to the millisecond.
- Lambda handles execution, scaling, and resource allocation.
- You can optimize performance by configuring the appropriate memory size for your function.

## How Lambda Works
1) Upload code to Lambda: (which then uploads as a Lambda function).
2) Set code to trigger from an event source. (events like AWS services, mobile apps, or HTTP requests).
3) Run code when triggered. (The Lambda runtime executes your function code using the event data passed to it).
4) Pay only for the compute time used.

## Lambda use cases
- Real-time image processing for a social media application.
- Personalized content delivery for a news aggregator.
- Real-time event handling for an online game.

# Containers and Orchestration on AWS
- Containers bundle the application with all of its dependencies and configuration, so it runs the same across different environments.
- Containers are faster and lighter than virtual machines (VMs) because they share the host computer’s operating system. VMs use a hypervisor to run full, separate operating systems, which makes them less resource-efficient and have longer startup times.

# AWS Container Services
1) Amazon Elastic Container Service (Amazon ECS): a scalable container orchestration service for running and managing containers on AWS, like Docker containers. (Docker is a software platform for building, testing, and deploying applications quickly). *Amazon ECS launch types*:
    - Amazon ECS with Amazon EC2 is ideal for small-to-medium businesses that need full control over infrastructure. Suitable for custom applications requiring specific hardware or networking configurations, with the flexibility of Amazon EC2 and the simplicity of Amazon ECS.
    - Amazon ECS with AWS Fargate is perfect for startups or small teams building web applications with variable traffic. It's a serverless option—no server management required—so teams can focus on development while Amazon ECS handles scaling and orchestration.

2) Amazon Elastic Kubernetes Service (Amazon EKS): Fully managed Kubernetes service for deploying and scaling containers. *Amazon EKS launch types*:
    - Amazon EKS with Amazon EC2: This is best for enterprises needing full control over infrastructure. It offers deep customization of EC2 instances alongside Kubernetes scalability—ideal for complex, large-scale workloads.
    - Amazon EKS with AWS Fargate: This is great for teams wanting Kubernetes flexibility without managing servers. It combines Kubernetes power with serverless simplicity, helping to scale applications quickly across various use cases.
3) Amazon Elastic Container Registry: Stores, manages, and deploys Open Container Initiative (OCI)-compliant container images.
4) AWS Fargate: Serverless compute engine for containers — removes the need to manage servers and allows devs focus on app development.


