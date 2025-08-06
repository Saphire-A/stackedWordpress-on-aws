# Stacked WordPress Deployment on AWS using CloudFormation
This project automates the deployment of a WordPress website hosted on Amazon EC2 using a custom CloudFormation template. It was developed as part of the Simplilearn AWS training program to demonstrate core infrastructure-as-code skills, automation with Lambda, and cost optimization through scheduling.

The deployment uses a local MySQL database installed on the same EC2 instance as WordPress (no RDS), with network isolation, a modular YAML template, and a scheduled auto-shutdown mechanism using Lambda and CloudWatch Events.

# Key Features
Infrastructure as Code using CloudFormation
EC2 instance provisioned with Apache, PHP, and WordPress
Custom VPC, Subnet, Security Group for secure network setup
Automated WordPress installation via UserData script
Lambda + CloudWatch scheduled shutdown to save cost
Visual validation through step-by-step screenshots
AMI creation for future replication of WordPress setup

# Documentation
File	Description
yamlcode_wordpresstemplate--cloudformationstack.pdf	CloudFormation template defining all infrastructure
screenshots.pdf	EC2 setup, WordPress login, Lambda, CloudWatch logs
Writeup.pdf	Explanation of implementation steps and key decisions

AWS Services Used
Amazon EC2 – WordPress and MySQL hosting (single instance)
Amazon VPC – Custom networking layer with a public subnet
Amazon CloudFormation – Defines and provisions AWS resources as YAML
AWS Lambda – Scheduled shutdown of EC2 to reduce cost
Amazon CloudWatch Events – Triggers Lambda on schedule

! Note: Amazon RDS and Load Balancer were not used in this implementation. The database runs locally on EC2, and scaling/load balancing were out of project scope.

# Learning Outcomes
Design and deploy modular AWS infrastructure using CloudFormation
Automate software setup via EC2 UserData scripting
Configure custom VPC and subnet layouts for isolated environments
Manage IAM roles and Lambda permissions
Schedule cost-saving actions with CloudWatch + Lambda
Create and use AMIs for reproducible instance setups
Debug failed stack deployments and security group issues

# Acknowledgements
Thanks to AWS and the Simplilearn platform for providing comprehensive training and cloud lab exposure that enabled this project.

# License: This project is licensed under the MIT License – see the LICENSE file for details.
