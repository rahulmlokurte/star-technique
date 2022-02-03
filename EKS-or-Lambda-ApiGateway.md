# AWS EKS vs AWS Lambda with Api Gateway

## Situation
We have 20 microservices running on-prem on PCF. The PCF licence needed to be renewed in 6 months.
Leadership wanted the project to migrate to AWS before that to save the cost and increase agility.

## Task
As a lead architect/developer/techlead, I was tasked to find out suitable AWS solutions for the project within
the time frame.

## Action
I researched possible ways to run microservices on AWS. I narrowed it down to three options.

- Run each microservice on vanilla EC2 instance.
- Run each microservice on kubernetes cluster using EKS.
- Serverless architecture using AWS Lambda and ApiGateway.

I took one of the microservices and did POC on vanilla EC2, EKS and Lambda-Api Gateway. 

## Result
While they all did the job, I found out the below:

- With EC2, I have to take care of making High Availability by spinning multiple instances in multiple Availability Zones.
- With EKS, it seemed valid solution. But due to low traffic pattern, we have to pay more than necessary.Also, there is an overhead
of training the team on Kubernetes.
- Lambda-Api Gateway is inherently Highly Available, scalable, and pay what I use and no server to manage at all. 
It simplifies our day2 operational overhead and let us focus on delivering business value.