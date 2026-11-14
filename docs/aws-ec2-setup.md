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

The initial configuration uses an AWS VPC and security group.

- Administrative SSH access is restricted to a trusted public IP address.
- HTTP and HTTPS inbound access are disabled.
- The Cowrie honeypot listener will be configured separately.
- Outbound traffic restrictions will be reviewed before the honeypot is exposed to the internet.

## EC2 Security

The configuration includes:

- SSH key-based authentication
- EBS volume encryption
- No default AWS service access
- IMDSv2-only configuration where instance metadata is enabled

