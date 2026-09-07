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
