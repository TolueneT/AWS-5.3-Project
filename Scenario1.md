# **Scenario 1 Project Answer;**

# **Infrastructure Solution that optimizes performance and minimizes latency for users in India and London regions.**

## 1. I use AWS Regions and Availability Zones:

- I ensured i deployed my application in multiple AWS regions, specifically in regions closest to my users, such as the Mumbai region for India and the London region for the UK.
- I use multiple Availability Zones (AZs) within each region to ensure high availability and fault tolerance.

## 2. Use of Global Load Balancing:

- I utilize Amazon Route 53 for DNS-based global load balancing. Route 53 can route users to the closest region based on latency.
- I configure health checks to ensure traffic is only routed to healthy endpoints.

## 3. Content Delivery Network (CDN):

- Use Amazon CloudFront as a CDN to distribute content globally with low latency.
- Configure CloudFront with edge locations close to the users (India and London) for caching static content.

## 4. Edge Caching:

- I wil use CloudFront to cache content at edge locations. This reduces the load on my origin servers and speeds up content delivery.
- Configure proper cache behaviors and TTL settings to optimize performance.

## 5. Region-Specific Deployment:

- Deploy your application infrastructure (compute, databases, storage) in both the Mumbai and London regions.
- Use services like Amazon EC2, Amazon RDS, and Amazon S3 to host your application and data.

## 6. Auto Scaling and Elasticity:

- Implement Auto Scaling groups in each region to handle varying loads dynamically.
- Use Elastic Load Balancing (ELB) within each region to distribute traffic across multiple instances.

## 7. Data Synchronization:

- Use Amazon RDS Multi-AZ for databases to ensure high availability.
- Implement cross-region replication for data synchronization between regions using AWS services like S3 Cross-Region Replication and RDS Read Replicas.

## 8. Monitoring and Logging:

- Use Amazon CloudWatch for monitoring and logging across all regions.
- Set up alarms and dashboards to monitor the health and performance of your infrastructure.

# _Infrastructure Diagram using draw.io_

![Infrastructure Diagram](images/AWS%20Multi-Region%20Infrastructure.jpg)

# **Implementation in AWS Console**

## 1. Set Up Route 53:

- Create a hosted zone.
- Configure latency-based routing policies.
