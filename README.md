# AWS Cowrie Honeypot — Threat Detection & Analysis

**AWS Cloud Security | Linux | Threat Intelligence | Splunk SIEM | Python | MITRE ATT&CK**

## Overview

This project documents the design, deployment, and analysis of an SSH honeypot hosted on Amazon Web Services (AWS).

The project uses Cowrie, an open-source SSH/Telnet honeypot, to simulate an interactive Linux environment and collect information about unauthorised access attempts and attacker behaviour.

Captured events will be analysed using Splunk SIEM, Python, and the MITRE ATT&CK framework.

## Project Objectives

- Deploy an Ubuntu Linux server using AWS EC2.
- Configure AWS network security controls and secure administrative access.
- Install and configure Cowrie to capture SSH attacks.
- Collect authentication attempts, attacker commands, and session information.
- Forward honeypot telemetry to Splunk.
- Develop SPL queries to detect suspicious behaviour.
- Analyse observed attacker techniques using MITRE ATT&CK.
- Automate log processing and analysis with Python.
- Document investigations and security findings.

## Technology Stack

| Technology | Purpose |
|---|---|
| AWS EC2 | Cloud infrastructure |
| Ubuntu 24.04 LTS | Linux operating system |
| Cowrie | SSH honeypot |
| AWS VPC / Security Groups | Network security |
| Splunk SIEM | Security monitoring and investigation |
| Python | Log analysis and automation |
| MITRE ATT&CK | Adversary behaviour mapping |
| Git / GitHub | Version control and documentation |

## Architecture

The planned architecture consists of:

Internet → AWS Security Group → EC2 Ubuntu → Cowrie Honeypot → Log Collection → Splunk SIEM

Administrative SSH access will be restricted, while the honeypot will be exposed through a separately configured listener. Outbound connectivity will be controlled to reduce the risk of misuse.

An architecture diagram will be added after deployment.

## Project Phases

- [ ] Phase 1: Deploy AWS EC2 infrastructure
- [ ] Phase 2: Configure Linux security and network isolation
- [ ] Phase 3: Install and configure Cowrie
- [ ] Phase 4: Configure security logging
- [ ] Phase 5: Integrate Cowrie with Splunk
- [ ] Phase 6: Develop SPL detection queries
- [ ] Phase 7: Investigate observed attacker activity
- [ ] Phase 8: Build Python analysis tools
- [ ] Phase 9: Publish investigation reports and findings

## Security Considerations

This project is conducted for authorised cybersecurity research and educational purposes.

The environment will use restricted administrative access, network controls, and isolated honeypot services.

Private SSH keys, AWS credentials, sensitive configuration values, and unredacted security logs will not be published.

## Current Status

**In progress — AWS infrastructure configuration**

This repository will be updated as each project phase is completed.

## Future Enhancements

- Infrastructure as Code using Terraform
- Automated threat intelligence enrichment
- Detection engineering and alert development
- MITRE ATT&CK technique mapping
- Security dashboards and investigation reports
