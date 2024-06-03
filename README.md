# AWS certification notes-Solution Architect AssociateC03

## EC2 - Elastic Cloud Computing
- Select based **compute, memory, storage** requirements
- Types:

|Type | Features | Potential Use Cases|
|-----|----------|---------------------|
| General purpose instances | equal compute, memory, storage | general applications (e.g. web servers, code repositories) |
| Compute optimised instances | ideal for compute-bound applications that need high-performance processors. Good to use them for batch processing workloads that require processing many transactions in a single group | more compute extensive operations (e.g.  high-performance web servers, compute-intensive applications servers, and dedicated gaming servers)|
| Memory optimised instances | more memory optimised, good for applications that are larger and need more memory | Workloads that requires large amounts of data to be pre-loaded before running, e.g .high performance database or large machine learning models |
| Accelerated computing instances | hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs (using GPUs too?) | floating-point number calculations, graphics processing, and data pattern matching (e.g. graphics applications, game streaming, and application streaming)|
| Storage optimised instances | handle high, sequential read and writ access to large datasets on local storage | distributed file systems, data warehousing applications, high frequency online transaction processing (OLTP) systems |
