# VPCShield
Deployed Jenkins on AWS EC2 and created a secure VPC for CI/CD automation
AWS VPC and Jenkins Deployment

## 📌 Project Overview

This project focuses on creating a secure AWS Virtual Private Cloud (VPC) and deploying Jenkins on AWS EC2 for automated CI/CD workflows. The implementation includes advanced security measures, such as Security Groups, Network ACLs (NACLs), and IAM roles, to ensure a robust and scalable deployment environment.

## 🚀 Key Achievements

🔹 VPC Creation
    
    Designed a custom VPC with a well-structured CIDR block.
    
    Configured public and private subnets for better resource segregation.
    
    Attached an Internet Gateway (IGW) for internet access.
    
    Configured Route Tables to control traffic flow between subnets.

🔹 EC2 Instance Setup

    Launched EC2 instances with optimized configurations.
    
    Configured EBS volumes for persistent storage.
    
    Deployed Jenkins on an EC2 instance to manage CI/CD pipelines.

🔹 Security Enhancements

    Managed Security Groups to allow only necessary traffic (SSH, HTTP, Jenkins ports).
    
    Implemented Network ACLs (NACLs) for granular subnet traffic control.
    
    IAM roles and policies assigned for least-privilege access control.
    
    Performed security testing by blocking inbound traffic using NACLs.

🔹 Jenkins Deployment & Configuration

    Installed Jenkins on AWS EC2 with required dependencies.
    
    Configured security settings to restrict unauthorized access.

🛠️ Technologies Used

    AWS Services: VPC, EC2, Security Groups, IAM, NACLs, Auto Scaling Groups.
    
    CI/CD Tools: Jenkins.

## Operating System: Linux (Ubuntu).

    📖 How to Recreate This Setup
    
    1️⃣ Create a Secure VPC
    
    Navigate to AWS VPC Console.
    
    Create a VPC with a custom CIDR block.
    
    Set up public and private subnets in different Availability Zones.
    
    Attach an Internet Gateway and update the Route Table.

2️⃣ Launch an EC2 Instance for Jenkins

    Go to AWS EC2 Console and launch an instance.
    
    Choose Ubuntu as the OS.
    
    Configure security groups to allow inbound traffic for SSH (22), HTTP (80), and Jenkins (8080).
    
    Attach the instance to the public subnet.

3️⃣ Install and Configure Jenkins

    SSH into the EC2 instance:
    
    ssh -i your-key.pem ubuntu@your-ec2-public-ip
    
    Update packages and install Java:
    
    sudo apt update && sudo apt install openjdk-11-jdk -y

## Install Jenkins:

    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt update
    sudo apt install jenkins -y

## Start and enable Jenkins:

    sudo systemctl start jenkins
    sudo systemctl enable jenkins

## Retrieve the initial admin password:

    sudo cat /var/lib/jenkins/secrets/initialAdminPassword

## Access Jenkins via http://your-ec2-public-ip:8080 and complete the setup.

🛡️ Security Measures Taken

Applied Security Groups to restrict unauthorized access.

Used NACLs to filter inbound and outbound traffic.

Implemented IAM roles for least-privilege access.

Enabled automatic backups for Jenkins data.

🎯 Lessons Learned & Takeaways

Deepened understanding of AWS networking and security best practices.

Improved knowledge of Jenkins CI/CD automation.

Gained hands-on experience with infrastructure security using AWS tools.

Successfully tested access control measures using Security Groups and NACLs.
