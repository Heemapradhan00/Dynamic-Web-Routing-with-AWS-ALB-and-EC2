# Dynamic-Web-Routing-with-AWS-ALB-and-EC2

This project demonstrates the setup of an AWS infrastructure using EC2 instances and an Application Load Balancer (ALB) to serve web applications for specific URL paths.

## Prerequisites

- **AWS Account**: Ensure you have an active AWS account.
- **Basic Knowledge**: Familiarity with AWS services like EC2, ALB, and Security Groups.
- **Tools**: Web browser or CLI tools like `curl` for testing.


## Features

1. **EC2 Instances**: 
   - Two separate instances, one serving `/api` and the other `/app`.
2. **Target Groups**:
   - Separate target groups for each path.
3. **Application Load Balancer**:
   - Internet-facing ALB configured with path-based routing for `/api` and `/app`.
4. **Security**:
   - Security groups configured for HTTP (port 80) access.

## Steps to Deploy

### Step 1: Launch EC2 Instances
1. Launch two EC2 instances using Amazon Linux 2 or Ubuntu AMIs.
2. Configure security groups to allow HTTP traffic (port 80).

### Step 2: Create Target Groups
1. Create one target group for `/api` and another for `/app`.
2. Register the respective EC2 instances to the target groups.

### Step 3: Set Up Application Load Balancer
1. Create an ALB with:
   - Internet-facing access.
   - Security group allowing HTTP traffic.
2. Configure the ALB listener for HTTP (port 80).

### Step 4: Configure Path-Based Routing
1. Add routing rules for:
   - `/api` -> Forward to `api-target-group`.
   - `/app` -> Forward to `app-target-group`.

### Step 5: Test the Deployment
1. Retrieve the ALB's DNS name from the AWS Management Console.
2. Test routing with a web browser or `curl`:
   - `/api`: `http://<ALB-DNS>/api`
   - `/app`: `http://<ALB-DNS>/app`



## Example URLs

- **/api**: `http://myapp-alb-1093081442.ap-south-1.elb.amazonaws.com/api`
- **/app**: `http://myapp-alb-1093081442.ap-south-1.elb.amazonaws.com/app`


## Author

**Heema Pradhan**  
Bachelor in Computer Application  
Medhavi Skills University, Sikkim  
