# AWS certification notes-Solution Architect AssociateC03

## EC2 - Elastic Cloud Computing
- Select based **compute, memory, storage** requirements
- Types of instances:

|Type | Features | Potential Use Cases|
|-----|----------|---------------------|
| General purpose instances | equal compute, memory, storage | general applications (e.g. web servers, code repositories) |
| Compute optimised instances | ideal for compute-bound applications that need high-performance processors. Good to use them for batch processing workloads that require processing many transactions in a single group | more compute extensive operations (e.g.  high-performance web servers, high performance computing (HPC), compute-intensive applications servers, and dedicated gaming servers, scientific modeling)|
| Memory optimised instances | more memory optimised, good for applications that are larger and need more memory | Workloads that requires large amounts of data to be pre-loaded before running, e.g .high performance database, large machine learning models, high-performance database |
| Accelerated computing instances | utilises hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs (using GPUs too?) | floating-point number calculations, graphics processing, and data pattern matching (e.g. graphics applications, game streaming, and application streaming)|
| Storage optimised instances | handle high, sequential read and writ access to large datasets on local storage | distributed file systems, data warehousing applications, high frequency online transaction processing (OLTP) systems |

- Types of pricing:
  
|Type | Scenario & Use Case | Flexibility | Pricing |
|-----|--------------------|---------|----|
|On-Demand | ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until stopped, and pay for only the compute time used. Good for developing and testing applications and running applications that have unpredictable usage patterns | High | High |
| Standard Reserved Instances | Known and fixed EC2 instance type, size needed and in which AWS Region | Low (lock in for 1 or 3 years) | Low |
| Convertible Reserved Instances | need to run  EC2 instances in different Availability Zones or different instance types | Medium (locked in but can have flexibility to change type and area) | Medium |
| Instance Savings Plans | make an *_hourly*_ spend commitment to an instance family and Region for a 1-year or 3-year term. Unlike Reserved Instances, there is no need to specify upfront what EC2 instance type and size. | Medium | Low (similar to Standard Reserved Instances, can be ~ 72% cheaper than On-Demand) |
| Spot Instances | ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer cost savings up to 90% off of On-Demand prices. | High | Low |
| Dedicated Hosts | physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. | Low | High (most expensive)|

- Types of scaling:
  - dynamic scaling: responds to changing demand
  - predictive scaling: schedules the right number of EC2 instances based on predicted demand
- Auto-scaling settings (note: pay for only the instances you use, when you use them):
  - Minimum capacity - number of EC2 instances that will always be the baseline when application is deployed
  - Maximum capacity - number of max EC2 instances that can go up to if needed
  - Desired capacity - defaults to min capacity, if indicated will try to scale up to desired when instance is available
 

## Elastic Load Balancer (ELB)
Single point of contact for all incoming web traffic to the Auto Scaling group. This means that as Amazon EC2 instances are added or removed in response to the amount of incoming traffic, these requests route to the load balancer first. Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it. 

## Amazon Simple Queue Service (SQS) or Simple Notification Service (SNS) - Message and Queue
- To reduce dependencies. monolithic application (components are highly interdependent) vs microservices (more loosely coupled and robust)
- SQS: send, store, received messages/payloads between software components at any volume. messages are placed until processed
- SNS: can send notification between services and also to end-users. through publish/subscribe model 
