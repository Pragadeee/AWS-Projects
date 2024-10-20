# AWS-Projects
In this project, I designed and implemented a Virtual Private Cloud (VPC) to ensure secure and scalable networking for cloud resources. I configured subnets, route tables, and network access control lists (NACLs) to segregate public and private resources. Additionally, I set up internet gateways, NAT gateways, and security groups to enable secure communication while controlling inbound and outbound traffic. The project ensured high availability and secure data flow between different instances and services, providing a robust cloud networking solution.

Step by step Process:

1.Create VPC 1 and VPC 2:

2.Define two Virtual Private Clouds (VPCs) with separate CIDR blocks. For example:
VPC 1: 172.16.0.0/16
VPC 2: 172.16.0.0/16

3.Create Subnets in Each VPC:

4.Create a public subnet in each VPC to host instances.
In VPC 1, create Public Subnet 1 with a range (e.g., 172.16.1.0/24).
In VPC 2, create Public Subnet 2 with a similar range (e.g., 172.16.2.0/24).

5.Configure Internet Gateways:


6.Attach an Internet Gateway to each VPC to allow instances to communicate with the internet:

7.Attach Internet Gateway 1 to VPC 1.

8.Attach Internet Gateway 2 to VPC 2.

9.Set Up Route Tables:

10.Create route tables for each VPC:

11.Route Table 1 in VPC 1 with routes that direct internet-bound traffic through Internet Gateway 1.

12.Route Table 2 in VPC 2 with routes pointing to Internet Gateway 2 for outbound internet traffic.

13.Implement Network ACLs:

14.Create Network ACLs (NACL) to control traffic at the subnet level:
NACL 1 for Public Subnet 1 (in VPC 1).
NACL 2 for Public Subnet 2 (in VPC 2).

15.Deploy EC2 Instances:

16.Launch an EC2 Instance in each subnet:
Instance 1 in Public Subnet 1 (VPC 1).
Instance 2 in Public Subnet 2 (VPC 2).

17.Configure Security Groups:

18.Set up Security Groups for both instances to control inbound and outbound traffic at the instance level:
Security Group for Instance 1 (VPC 1) with rules to allow inbound traffic from the internet or specific sources.
Security Group for Instance 2 (VPC 2).

19.VPC Peering Connection:

Establish a VPC Peering Connection between VPC 1 and VPC 2 to enable direct communication between instances in different VPCs.

20.Update the route tables of both VPCs to include routes for the CIDR ranges of the peer VPC.

21.Enable VPC Flow Logs:

Configure VPC Flow Logs to capture detailed information about the traffic flowing through VPC 1 and VPC 2.
Store the flow logs in Amazon CloudWatch for monitoring and analysis.

22.Monitor with CloudWatch:

Set up monitoring for both VPCs using CloudWatch to track network traffic and resource usage.

23.Use VPC Flow Logs in CloudWatch for security and troubleshooting purposes.
