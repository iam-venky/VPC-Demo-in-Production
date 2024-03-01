# VPC-Demo-in-Production
The steps to create a VPC with 2 public and 2 private subnets, 2 NAT gateways across two availability zones, an Application Load Balancer, and an Auto Scaling Group.
# Overview
The VPC has public subnets and private subnets in two Availability Zones.
Each public subnet contains a NAT gateway and a load balancer node.
The servers run in the private subnets, are launched and terminated by using an Auto scaling group, and receive traffic from the load bvalancer.
The servers can connect to the internet by using The NAT gateway.

