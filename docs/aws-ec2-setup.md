# AWS EC2 Infrastructure Setup

## Overview

This document records the configuration of an Amazon EC2 virtual machine intended to host the Cowrie SSH honeypot.

## Infrastructure Configuration

| Component | Configuration |
|---|---|
| Cloud provider | Amazon Web Services (AWS) |
| Region | ap-southeast-2 |
| EC2 instance name | cowrie-honeypot |
| Operating system | Ubuntu Server 24.04 LTS |
| Architecture | x86-64 |
| Instance type | t3.small |
| vCPUs | 2 |
| Memory | 2 GiB |
| Storage | 20 GiB gp3 EBS |
| Encryption | AWS-managed EBS KMS key |
| Authentication | SSH key pair |
| Public IPv4 | Enabled |

## Network Security

The EC2 instance is deployed within an AWS Virtual Private Cloud (VPC) and protected by an EC2 security group.

- Administrative SSH (TCP/22) is restricted to a trusted public IP address using a `/32` CIDR rule.
- HTTP (TCP/80) and HTTPS (TCP/443) inbound access are disabled.
- The Cowrie SSH honeypot listener will be configured separately on TCP/2222.
- Outbound traffic restrictions will be reviewed before exposing the honeypot to the internet.
- Administrative access uses SSH public-key authentication rather than password-based authentication.

## EC2 Security

The configuration includes:

- SSH key-based authentication
- EBS volume encryption
- No default AWS service access
- EC2 Instance Metadata Service (IMDSv2) enforced with token-based authentication and a response hop limit of 1.


