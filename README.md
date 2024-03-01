# VPC-Demo-in-Production

The steps to create a VPC with 2 public and 2 private subnets, 2 NAT gateways across two availability zones, an Application Load Balancer, and an Auto Scaling Group.

# Overview

The VPC has public subnets and private subnets in two Availability Zones.
Each public subnet contains a NAT gateway and a load balancer node.
The servers run in the private subnets, are launched and terminated by using an Auto scaling group, and receive traffic from the load bvalancer.
The servers can connect to the internet by using The NAT gateway.

# Create a VPC:

Go to the AWS Management Console and navigate to the VPC service.
Click on "Create VPC" and enter the desired details like VPC name, CIDR block (e.g., 10.0.0.0/16).
Created two public subnets and two private subnets in different availability zones within the VPC.
Ensure that the public subnets have a route to an internet gateway for internet access.
Associate the subnets with the route table.

# Create Auto Scaling Group

Created an Auto Scaling Group with desired configurations (e.g., launch Configuration, instance type, minimum and maximum instances).
Specify the two private subnets for the Auto Scaling Group to launch instances.

# Create a Bastian Host

Created a bastion host to connect to an EC2 instance hosted in a private subnet.
Launch a new EC2 instance to act as the bastion host in a public subnet.
Used this command to copy .pem to Bastian host:
scp -i /Users/venkatesh.dhonakanti.CORP/Downloads/vpckeypair.pem /Users/venkatesh.dhonakanti.CORP/Downloads/vpckeypair.pem ubuntu@3.237.93.68:/home/ubuntu
SSH into the bastion host using the public IP or Elastic IP assigned to it. From the bastion host, SSH into the private EC2 instance using its private IP address.

# Install Basic python Application

Created a index.html file in one of the instance in private subnet and installed basic python application in it.

# Create a Load balancer

Created an Application Load Balancer (ALB) in over two public subnets.
Created a target group including two instances. 
Configure the ALB to distribute traffic to the instances in the private subnets.

By following these steps, you should be able to set up the VPC in AWS with public and private subnets, NAT gateways, load balancers, and auto-scaling groups as per the specified configuration.
