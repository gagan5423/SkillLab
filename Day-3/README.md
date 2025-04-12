Session - 3  
Terraform Script

Terraform is an IAC (Infrastructure as Code) tool.  
Whenever you want to create cloud resources like EC2, VPC, subnets, load balancers, database servers using automation or script, Terraform is used.

Setting up Terraform:  
- Install Terraform on Windows machine  
- Set Terraform path  
- Configure AWS credentials from CLI (Install AWS CLI)  

AWS CLI Configuration:  
- Access key and secret key from downloaded .csv  
- Region code: ap-south-1  
- Default output format: (leave empty)

IAM  
- IAM role permissions: EC2 full access, VPC full access  
- Access keys  
- Download .csv  

Terraform Scripting  
- Open folder in VS Code  
- Create .tf files  

Terraform Blocks:  
- Provider Block: Specifies the cloud platform (AWS, Azure, GCP)  
- Resource Block: Specifies the type of resource (EC2, VPC, subnets, etc.)  
- Variable Block: Pass parameters  
- Output Block: Print outputs like public/private IP, VPC ID, etc.

Instance Creation Parameters:  
- Amazon AMI ID  
- Instance Type  
- Key-Pair Name  
- Storage  
- Instance Name  

Terraform Commands:  
- Initialize Terraform  
- Validate the script  
- Preview changes  
- Apply the configuration  
- Delete resources  

Important Notes:  
- State file stores current infrastructure state  
- It must be secured to avoid unauthorized access  

AWS Concepts:  
- ARN: Amazon Resource Name  
- VPC: Virtual Private Cloud  

Terraform Architecture Overview:  
- Create VPC  
- Availability Zone  
- Subnet  
- IP Address  

VPC Creation Example:  
- VPC name: tarun-vpc  
- CIDR block: 10.0.0.0/16  
- Tenancy: default  
- Subnet:  
  - CIDR block: 10.0.1.0/24  
  - Subnet name: tarun-subnet  
  - Availability zone: ap-south-1a  

Script Structure:  
- main.tf  
- variables.tf  
- output.tf  

Docker  
Docker is a containerization tool used to create portable, platform-independent applications using OS-level virtualization.

Benefits:  
- Reduce server cost  
- Run applications anywhere  
- Divide applications into microservices  

Microservices vs Monolithic:  
Monolithic:  
- Single-tier architecture  
- Web server, app server, DB combined  
- Tightly coupled — failure in one module impacts the whole system  

Microservices:  
- Loosely coupled independent services  
- If one fails, others still function  
- Each service runs in a separate container  

Issues with Microservices:  
- Higher cost due to separate servers for each service  

Docker Use Cases:  
- Reduces cost  
- Efficient resource usage  
- Platform independence  
- Portability  
- Build Once, Run Anywhere

Docker Desktop:  
- Requires WSL