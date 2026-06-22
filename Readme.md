Project Agenda:
Demonstrate how to connect to a Private RDS instance using a public ec2 Instance.
Project Overview:
 I implemented a 3-tier architecture that integrates a private RDS database with both public and private EC2 instances. Network connectivity is established via a public EC2 instance acting as a jump server, enabling secure access to the private resources.
Architecture Components:
• Public Instance: Serves as a secure gateway to access the private EC2 application server and the RDS database. 
• Application Instance (Private): Not directly accessible from the internet; access is strictly routed through the jump instance. 
• RDS Database (Private): Designed to store and retrieve large volumes of data securely within the private network
Infrastructure Requirements
 • 1 VPC (Virtual Private Cloud) 
• 6 Subnets: 
     o 2 Public 
     o 2 Private (Application Server)
     o 2 Private (RDS) 
• 2 Route Tables:
      o 1 for Public Connectivity 
      o 1 for Private Connectivity 
• 1 Internet Gateway for external access 
• 1 NAT Gateway for secure outbound traffic from private subnets 
• 2 Security Groups:
     o 1 for Public Access
     o 1 for Private Resources 
• 2 Load Balancers:
   o 1 Public 
o 1 Private 
• 2 Auto Scaling Groups: 
      o 1 Public 
      o 1 Private
 • 1 AMI Template for EC2 instance deployment 
• 4 EC2 Instances: 2 Public Servers, 2 Private (Application Servers)
