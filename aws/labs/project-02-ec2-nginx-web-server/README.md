# Project 02 — EC2 Linux Web Server with Nginx

## Overview

This project demonstrates how to launch an Amazon EC2 instance, connect to it securely using SSH, install and configure Nginx, and host a simple static website.

The goal of this project was to turn AWS EC2 and Linux theory into practical hands-on experience.

---

## Architecture

Browser → Internet → Security Group → Amazon EC2 → Amazon Linux 2023 → Nginx → Static Website

---

## AWS Services and Technologies

- Amazon EC2
- Amazon Linux 2023
- Security Groups
- SSH
- Nginx
- HTML
- Linux
- Git/GitHub

---

## Instance Configuration

- AMI: Amazon Linux 2023
- Instance type: t3.micro
- Storage: 8 GiB gp3
- Public IPv4 enabled
- Default VPC
- Key pair authentication using `.pem`

---

## Security Group

The EC2 instance uses a dedicated security group.

### Inbound Rules

| Type | Protocol | Port | Source |
|---|---|---:|---|
| SSH | TCP | 22 | My IP only |
| HTTP | TCP | 80 | 0.0.0.0/0 |

SSH access was restricted to my public IP instead of allowing access from anywhere.

HTTP port 80 was opened publicly so users could access the website.

---

## Steps Completed

### 1. Launch EC2 Instance

Created a new Amazon EC2 instance using Amazon Linux 2023.

### 2. Create SSH Key Pair

Created an RSA key pair using the `.pem` format.

The private key was stored securely on the local machine and was not uploaded to GitHub.

### 3. Configure Security Group

Configured:

- SSH on port 22 from my IP only
- HTTP on port 80 from anywhere

### 4. Connect Using SSH

Connected to the EC2 instance from Git Bash using:

```bash
ssh -i "project-02-nginx-key.pem" ec2-user@<public-dns>