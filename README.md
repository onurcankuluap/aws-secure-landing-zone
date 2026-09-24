# Secure AWS Landing Zone

A hands-on AWS cloud security project focused on building a small but realistic public/private architecture with controlled ingress, private compute, secure administration, and load-balanced application delivery.

## Overview

The goal of this project was to deploy a web application in AWS without exposing the application server directly to the internet.

The final design uses:

- a custom VPC
- two public subnets
- two private subnets
- an internet-facing Application Load Balancer
- a private EC2 instance
- security group segmentation
- EC2 Instance Connect Endpoint for private administration
- an S3 Gateway Endpoint for package access
- an Apache web server on Amazon Linux 2023

The application is publicly reachable through the load balancer, while the EC2 instance remains private.

---

## Architecture

```text
Internet
   |
   v
Application Load Balancer
   |
   |-- Public A
   |-- Public B
   |
   v
portfolio-app-sg
   |
   v
Private EC2
Private A
   |
   v
Apache Web Server
