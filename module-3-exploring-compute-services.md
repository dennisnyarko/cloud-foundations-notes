# Introduction to Serverless Computing
- With serverless computing, you run applications without managing the underlying infrastructure
- Unmanaged services: like Amazon EC2, AWS takes care of the underlying physical infrastructure, but you're responsible for setting up, securing, and maintaining the operating system, network configurations, and applications on your instances.
- Managed services: handlex most of the infrastructure for you, but you still need to set up things like deployment options, scaling, and environment settings.
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
