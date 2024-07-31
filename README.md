# Ansible-infrastructure
Deploy to AWS using ansible
USing the set up image as a guide.

The playbook provided is designed to create several AWS resources. Here is a comprehensive list of the resources that the playbook will create:

VPC (Virtual Private Cloud):

A new VPC with a specified CIDR block.
Subnets:

Three public subnets in different availability zones.
Three private subnets in different availability zones.
Internet Gateway:

An Internet Gateway attached to the VPC.
Route Tables:

A public route table associated with the public subnets and configured with a route to the Internet Gateway.
A private route table associated with the private subnets and configured with a route to the NAT Gateway.
NAT Gateway:

A NAT Gateway in one of the public subnets for outbound internet access from private subnets.
Security Groups:

A security group for the RDS instance.
A security group for the ELB.
RDS (Relational Database Service) Resources:

An RDS subnet group that includes the private subnets.
An RDS instance configured with multi-AZ deployment.
An RDS read replica in a secondary region.
ELB (Elastic Load Balancer):

An ELB with listeners configured to distribute traffic across instances in multiple availability zones.
S3 (Simple Storage Service) Bucket:

An S3 bucket for backups with a unique name.
RDS Snapshot:

A snapshot of the RDS instance uploaded to the S3 bucket.




commands to run the infrastucture creation 
ansible-playbook vpc_setup.yml

command to destroy all the created infrastructure according to the playbook
ansible-playbook destroy_playbook.yml
