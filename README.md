![Alt text](/Host_a_Static_Website_on_AWS.png)

### Host a Static Website on AWS

This repository contains scripts and configurations to host a static HTML web app on AWS using various services and resources. Below is an overview of the setup and deployment process.

#### Project Overview:
- **Objective**: Host a static website on AWS infrastructure with enhanced security, scalability, and fault tolerance.
- **GitHub Repository**: [Link to Repository](https://github.com/ascendesys/host-a-static-website-on-aws)

#### Deployment Steps:

1. **Configure Virtual Private Cloud (VPC)**:
   - Created a VPC with public and private subnets spanning multiple availability zones for high availability and fault tolerance.

2. **Internet Connectivity**:
   - Deployed an Internet Gateway to enable connectivity between VPC instances and the Internet.

3. **Security Mechanisms**:
   - Implemented Security Groups to act as a firewall mechanism for network security.

4. **High Availability**:
   - Utilized two Availability Zones to enhance system reliability.

5. **Networking Setup**:
   - Leveraged Public Subnets for components like NAT Gateway and Application Load Balancer.
   - Positioned EC2 instances within Private Subnets for enhanced security.

6. **Secure Connections**:
   - Implemented EC2 Instance Connect Endpoint for secure connections within public and private subnets.

7. **Internet Access for Private Subnets**:
   - Enabled instances in private subnets to access the Internet via the NAT Gateway.

8. **Website Hosting**:
   - Hosted the static website on EC2 instances.

9. **Load Balancing and Scaling**:
   - Utilized an Application Load Balancer and a target group to evenly distribute web traffic to an Auto Scaling Group of EC2 instances across multiple Availability Zones.
   - Employed Auto Scaling Group for automatic management of EC2 instances, ensuring website availability, scalability, fault tolerance, and elasticity.

10. **Version Control**:
    - Stored web files on GitHub for version control and collaboration.

11. **Security Measures**:
    - Secured application communication using a Certificate Manager.

12. **Monitoring and Alerts**:
    - Configured Simple Notification Service (SNS) to alert about activities within the Auto Scaling Group.

13. **Domain Setup**:
    - Registered a domain name and set up a DNS record using Route 53.

#### Deployment Script:
```bash
#!/bin/bash
# Switch to the root user to gain full administrative privileges
sudo su
# Update all installed packages to their latest versions
yum update -y
# Install Apache HTTP Server
yum install -y httpd
# Change the current working directory to the Apache web root
cd /var/www/html
# Install Git
yum install git -y
# Clone the project GitHub repository to the current directory
git clone https://github.com/ascendesys/host-a-static-website-on-aws.git
# Copy all files, including hidden ones, from the cloned repository to the Apache web root
cp -R host-a-static-website-on-aws/. /var/www/html/
# Remove the cloned repository directory to clean up unnecessary files
rm -rf host-a-static-website-on-aws
# Enable the Apache HTTP Server to start automatically at system boot
systemctl enable httpd
# Start the Apache HTTP Server to serve web content
systemctl start httpd
```

#### Notes:
- Make sure to replace placeholders with actual values where necessary (e.g., GitHub repository link, domain name).
- Ensure proper IAM permissions are set for accessing AWS resources.
- Regularly monitor AWS resources for optimal performance and cost management.

Feel free to contribute to and enhance this project for further improvements and functionalities. If you encounter any issues or have suggestions, please open an issue in the repository for discussion and resolution.

**Author:** [Gori Adenuga]  
**Contact:** [yadenuga@yahoo.com]  

