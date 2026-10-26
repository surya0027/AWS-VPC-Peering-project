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
| VPC-A CIDR | `28.0.0.0/16` |
| VPC-A Public Subnet | `28.0.1.0/24` |
| VPC-A Private Subnet | `28.0.2.0/24` |
| VPC-B CIDR | `28.200.0.0/16` |
| VPC-B Private Subnet | `28.200.1.0/24` |
| AWS Region | Asia Pacific (Mumbai), `ap-south-1` |

## AWS Services Used

- Amazon VPC
- Amazon EC2
- VPC Peering
- Subnets
- Route Tables
- Internet Gateway
- Security Groups
- Network ACLs
- EC2 Instance Connect Endpoint (temporary, deleted after testing)

## Implementation

1. Created VPC-A and VPC-B.
2. Created the required subnets.
3. Attached an Internet Gateway to VPC-A.
4. Created and accepted the VPC Peering connection.
5. Added routes to the peer VPC CIDR ranges in the route tables.
6. Configured security groups to allow the required traffic.
7. Launched EC2 instances in both VPCs.
8. Connected to the private EC2 instance using a temporary EC2 Instance Connect Endpoint to perform the reverse connectivity test.

## Connectivity Testing

Connectivity was tested between the EC2 instances using their private IP addresses.

- **VPC-A to VPC-B:** Ping successful — `0% packet loss`.
- **VPC-B to VPC-A:** Ping successful — `0% packet loss`.

These results confirm bidirectional private-IP connectivity between the EC2 instances through VPC Peering.

## Screenshots

## Screenshots

Screenshots documenting the VPCs, subnets, peering connection, route tables, EC2 instances, security groups, and connectivity tests are included in this repository.

1. `01-vpc-a.png` — VPC-A configuration
2. `02-vpc-b.png` — VPC-B configuration
3. `03-public-subnet-vpc-a.png` — VPC-A public subnet
4. `04-private-subnet-vpc-a.png` — VPC-A private subnet
5. `05-private-subnet-vpc-b.png` — VPC-B private subnet
6. `06-vpc-peering-active.png` — Active VPC Peering connection
7. `07-route-table-vpc-a.png` — VPC-A route table
8. `08-route-table-vpc-b.png` — VPC-B route table
9. `09-ec2-vpc-a.png` — EC2 instance in VPC-A
10. `10-ec2-vpc-b.png` — EC2 instance in VPC-B
11. `11-security-group-vpc-a.png` — VPC-A security group
12. `12-security-group-vpc-b.png` — VPC-B security group
13. `13-ping-a-to-b.png` — VPC-A to VPC-B ping test
14. `14-ping-b-to-a.png` — VPC-B to VPC-A ping test
15. `15-vpc-peering-architecture.png` — VPC Peering architecture diagram

## Conclusion

The project demonstrates private network communication between two VPCs through VPC Peering. The VPC-B EC2 instance communicated with the VPC-A EC2 instance using private IP addressing without requiring a public IP address on the VPC-B instance.

## Security and Cleanup

- Both EC2 instances were stopped after testing.
- The temporary EC2 Instance Connect Endpoint was deleted after testing.
- No private keys, passwords, or AWS access credentials are included in this repository.
