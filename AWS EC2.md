## Before EC2
In the 1980s and 1990s:
1. Obtaining a server required several months.
2. The turnaround time was long.
3. Performance and maintenance issues.
4. Server failure rates were high, and fixing an issue was never easy.
5. No option to scale up and down as needed.

In the 2000s:
1. Virtualization came into existence to address problems with physical servers.
2. It also supported better system maintenance and faster recovery time.

In 2006:
1. Cloud computing came into existence.
2. AWS offered Amazon Elastic Compute Cloud (EC2).
3. It provides virtual servers in the cloud, allowing users to run applications and services without the need to invest in physical hardware or manage their own data centers.
4. EC2 is a web service that provides resizable compute capacity in the cloud.
5. This allows users to create and configure VMs, known as instances, based on specific needs.
6. These instances can be provisioned with different configurations, like the amount of CPU, memory, storage, and network capacity.

## EC2 features:
1. Instances are available in various instance types, each optimized for different use cases.
2. Pay as you use.
3. No upfront costs, no long-term commitments, cost-effective for small startups as well as large enterprises.
4. Robust infrastructure that ensures high availability and reliability.
5. Instances can be spread across multiple data centers, providing redundancy and fault tolerance.
6. Helps distribute traffic and automatically adjust resources to maintain performance and availability.
7. Wide range of instance types like OS, software configurations, etc.
8. Instances integrate seamlessly with other AWS services such as S3, RDS for databases, VPC for networking, and so on.

## AWS Regions
1. Within AWS Cloud, AWS regions are available.
2. They are isolated from each other.
3. This way, the design achieves high fault tolerance and stability.
4. Automatic replication of resources across regions is not done.
5. Within each region, availability zones from A to Z are available. These are physically isolated data centers to achieve high availability within a region.
6. The AWS Backbone network is a global, high-capacity, highly reliable network infrastructure that interconnects Amazon Web Services data centers and network points of presence worldwide.

## VPC
1. AWS VPC is a service that lets you set up a private, isolated section within AWS Cloud to securely run resources.
2. Each VPC provides logical isolation and acts as a private network within the AWS Cloud.
3. You can customize various network settings to your specific requirements.
4. A secure connection can be established between a VPC and an on-premises data center using a VPN, which results in a hybrid-cloud setup.
5. VPCs can also be connected together using VPC peering. This enables communication between them within the cloud.
6. A VPC can be further divided into subnets to manage the network effectively for routing and application segregation based on the requirements.
7. A subnet is always associated with an availability zone.
8. Route tables help apps within a VPC to talk to apps within a different VPC or elsewhere.

## Security Group 
1. A security group verifies incoming requests and allows traffic only if it is authorized to access the system.
2. Two types of rules in a security group: inbound rules and outbound rules.
3. Three main components of the security group: protocol, port range, and source.

## NACL (Network Access Control Lists)
1. This is used to gain fine-grained access control.
2. Two types of rules in NACLs: inbound rules and outbound rules.
3. NACLs are stateless, so the outbound rule for every inbound rule must be explicitly mentioned.
4. Best to use both security groups and NACLs according to the use case for better security.

## AMI (Amazon Machine Image)
1. It is a snapshot or clone of a virtual server in the cloud.
2. Everything is captured, including the OS, software, data, and configuration.
3. It can be saved and reused to create new EC2 instances in AWS.
4. AMIs can be obtained for free or paid from the AWS Marketplace.
5. Advantages of AMI:
   1. Easily replicate virtual servers in AWS.
   2. Create identical instances quickly and efficiently.
   3. No chance of errors or inconsistencies.
   4. AMIs support versioning that allows you to manage updates and changes over time or maintain different versions for different purposes.
  
## Instance types
### Amazon EC2 Instance Families

| Category | Identifier Prefixes | Primary Resource / Optimization | Best Used For |
| :--- | :--- | :--- | :--- |
| **General Purpose** | **M**, **T** (Burstable), **Mac** | Balanced Compute, Memory, and Networking | Small-to-medium databases, backend web servers, code repositories, development environments, and macOS application building. |
| **Compute Optimized** | **C** | High-Performance Processors / CPU | Batch processing, media transcoding, high-traffic web servers, dedicated game servers, scientific modeling, and machine learning inference. |
| **Memory Optimized** | **R**, **X**, **U** (High Memory), **z1d** | High RAM capacity | In-memory databases (e.g., Redis), real-time big data analytics (e.g., Apache Spark), SAP workloads, and massive caching layers. |
| **Storage Optimized** | **I** (IOPS), **D** (Dense), **H** (High Throughput) | Local NVMe/SSD storage or sequential read/write throughput | High-throughput distributed databases (e.g., Cassandra), data warehouses, log processing applications, and large-scale network file systems. |
| **Accelerated Computing** | **P**, **G**, **Trn**, **Inf**, **F** | Hardware Co-processors (GPUs, FPGAs, Trainium, Inferentia) | Generative AI training, Deep Learning model deployment, 3D graphics rendering, video encoding, and hardware acceleration. |
| **HPC Optimized** | **Hpc** | High-performance clustered networking and compute scales | Large-scale High-Performance Computing workloads, complex fluid dynamics, and molecular simulations. |

---

### Understanding the Identifier Suffixes (e.g., m7g.xlarge)

* **`a`**: AMD EPYC processors
* **`g`**: AWS Graviton processors (ARM-based)
* **`i`**: Intel Xeon processors
* **`d`**: Local NVMe storage included
* **`n`**: Network optimized (extra bandwidth)

### Amazon EC2 Instance Sizes

| Size Identifier | vCPU Scale | RAM Scale | Best Used For |
| :--- | :--- | :--- | :--- |
| **nano** | 1 vCPU | 0.5 GiB | Low-traffic websites, simple microservices, and tiny testing environments. |
| **micro** | 1 - 2 vCPUs | 1 - 2 GiB | Free-tier experimentation, light development, and small background cron jobs. |
| **small** | 2 vCPUs | 2 - 4 GiB | Dev/QA environments and low-load application servers. |
| **medium** | 2 vCPUs | 4 - 8 GiB | Entry-level production applications and small database instances. |
| **large** | 2 vCPUs | 8 - 16 GiB | Standard application backends, staging systems, and container nodes. |
| **xlarge** | 4 vCPUs | 16 - 32 GiB | Mid-tier production traffic, relational databases, and enterprise applications. |
| **2xlarge** | 8 vCPUs | 32 - 64 GiB | High-traffic applications, heavy batch-processing, and production databases. |
| **4xlarge** to **16xlarge** | 16 - 64 vCPUs | 64 - 256 GiB | Large distributed systems, big data analytics workers, and heavy enterprise ERP clusters. |
| **24xlarge** to **48xlarge** | 96 - 192 vCPUs | 384 - 768 GiB | Massive monolithic applications, high-end databases, and large-scale rendering workloads. |
| **metal** | Full Host | Full Host | Bare-metal access directly to underlying hardware, skipping the hypervisor layer for maximum performance or custom licensing. |


1. Benefits:
   1. Performance optimization.
   2. Cost optimization.
   3. Specialized workloads.
   4. Scalability and flexibility.
   5. Architecture Optimization

## EC2 storage
1. Amazon EC2 provides flexible, cost-effective, and easy-to-use data storage options for instances.
2. Each option has a unique combination of performance and durability.
3. Can be used independently or in combination based on requirements.
4. Commonly available storage options: Instance store, EBS (Elastic Block Store), or EFS (Elastic File System)

### Instance store
1. Some EC2 instance types come with temporary storage known as instance store.
2. These volumes provide high-performance, low-latency storage that is physically attached to the EC2 server.
3. These volumes are not persistent and are lost if the EC2 instance is stopped, terminated, or fails.
4. Useful for temporary data, caching, and scratch space.

### EFS (Elastic File System)
1. Provides scalable file storage for use with EC2 instances.
2. Can be used as a common data source for all workloads and applications running on multiple instances.
3. Size can be increased or decreased dynamically based on usage.
4. Pay only for the usage.


### EBS (Elastic Block Store)
1. Provides block-level storage volumes that can be attached to EC2 instances.
2. Highly durable and persistent, they can retain data even if the EC2 instance is stopped or terminated.
3. EBS volumes offer different types, optimized for different workloads, such as SSD.
4. Provisioned IOPS are designed to meet the needs of IO intensive workloads that are sensitive to storage performance and consistency.
5. Features of EBS:
   1. Data availability:
      1. When an EBS volume is created, it is automatically replicated within the availability zone to prevent data loss due to failure of any single hardware component.
      2. An EBS volume can be attached to any EC2 instance in the same availability zone.
      3. After the volume is attached, it appears as a native block device, so the EC2 instance can interact with the volume just as it would with a local drive.
    2. Data Persistence:
       1. An EBS volume is off-instance storage that can persist independently of the life of an instance.
       2. Payment for the volume usage is charged as long as the data persists.
    3. Disk Encryption: Encrypted EBS volumes can be used to meet a wide range of data-at-rest encryption requirements for regulated data and applications.
    4. Snapshots: EBS provides the ability to create snapshots for any EBS volume and write a copy of the data in the volume to Amazon S3. Modifications can be done without service interruption.
