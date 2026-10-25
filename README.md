# AWS VPC Peering Project

## Project Overview
This project demonstrates how to connect two Amazon Virtual Private Clouds (VPCs) using VPC Peering and enable private IP communication between EC2 instances.

## Objectives
- Create two VPCs with separate CIDR ranges.
- Configure public and private subnets.
- Create and accept a VPC Peering connection.
- Configure route tables for communication between VPCs.
- Launch EC2 instances and test connectivity using ping.

## Network Configuration

| Resource | Configuration |
|---|---|
| VPC-A CIDR | 28.0.0.0/16 |
| VPC-A Public Subnet | 28.0.1.0/24 |
| VPC-A Private Subnet | 28.0.2.0/24 |
| VPC-B CIDR | 28.200.0.0/16 |
| VPC-B Private Subnet | 28.200.1.0/24 |
| AWS Region | Asia Pacific (Mumbai), ap-south-1 |

## AWS Services Used
- Amazon VPC
- Amazon EC2
- VPC Peering
- Subnets
- Route Tables
- Internet Gateway
- Security Groups
- Network ACLs

## Implementation
1. Created VPC-A and VPC-B.
2. Created the required subnets.
3. Attached an Internet Gateway to VPC-A.
4. Created and accepted the VPC Peering connection.
5. Added routes to the peer VPC CIDR ranges in the route tables.
6. Configured security groups to allow the required traffic.
7. Launched EC2 instances in both VPCs.

## Connectivity Testing
Connectivity was tested between the EC2 instances using their private IP addresses.

- From VPC-A to VPC-B: Ping successful.
- From VPC-B to VPC-A: Ping successful.
- Packet loss during the successful tests: 0%.

## Conclusion
The project demonstrates private network communication between two VPCs through VPC Peering without requiring a public IP address on the VPC-B EC2 instance.

## Security Note
EC2 instances were stopped after testing. No private keys, passwords, or AWS access credentials are included in this repository.
