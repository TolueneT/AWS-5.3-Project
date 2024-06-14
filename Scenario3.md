# **Analysis of Existing On-Premises Infrastructure**

# _Challenges and Shortcomings:_

1. Single Point of Failure:

- Both the application and the database are hosted on the same VM, making the entire setup vulnerable to failures. If the server goes down, both the application and database become unavailable.

2. Lack of Scalability:

- The current infrastructure cannot scale to handle peak traffic during weekends, leading to performance degradation and downtime.

3. Security Vulnerabilities:

- Running both the application and the database on the same server exposes the system to potential security breaches. An attack on the application could compromise the database as well.

4. Inefficient Resource Allocation:

- Hosting both the application and the database on a single VM can lead to resource contention, affecting performance. Resources are not optimally utilized.

# **Proposed Cloud-Native Solution**

# _Objectives:_

1. Eliminate Single Points of Failure:

- Separate the application and database into different environments to ensure that a failure in one does not affect the other.

2. Scalability:

- Use cloud-native services to automatically scale the application based on demand.

3. Security:

- Implement security best practices, such as network segmentation, access controls, and encryption.

4. Efficient Resource Allocation:

- Optimize resource allocation by leveraging cloud services that can dynamically adjust to the workload.

# **Solution Architecture**

1. Application Layer:

- Cloud Provider: AWS
- Service: Amazon EC2 Auto Scaling Group
- Load Balancer: Application Load Balancer (ALB)
- Compute Instances: EC2 instances running the legacy application

2. Database Layer:

- On-Premises: Retain the MySQL database on-premises
- Connectivity: Use AWS Direct Connect or a VPN for secure communication between the on-premises database and the cloud application

3. Security:

- Network Segmentation: Use Virtual Private Cloud (VPC) to isolate the application environment
- Access Control: Implement Security Groups and Network ACLs to control inbound and outbound traffic
- Encryption: Encrypt data in transit using SSL/TLS and at rest

4. Monitoring and Logging:

- Use CloudWatch for monitoring application performance
- Use AWS CloudTrail for logging and auditing activities

# **Architectural Diagram**

![Architectural Diagram](images/Scenario3.jpg)

# **Implementation Steps**

# _Step 1: Set Up AWS Environment_

1. Create a VPC:

- Set up a Virtual Private Cloud (VPC) to host your application instances.

2. Set Up Subnets and Routing:

- Create public and private subnets for your VPC.
- Configure route tables and internet gateways.
