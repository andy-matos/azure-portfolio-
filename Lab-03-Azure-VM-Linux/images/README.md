🚀 Lab 03 – Deploying and Securing a Linux Virtual Machine in Azure
📌 Overview

This lab demonstrates the deployment of a Linux Virtual Machine in Microsoft Azure using Infrastructure as a Service (IaaS).

The objective was to configure secure SSH access, deploy a web server (NGINX), expose it to the internet through proper network rules, and understand the underlying Azure networking components.

🎯 Objectives

Deploy an Ubuntu 24.04 LTS Virtual Machine in Azure

Configure SSH key-based authentication

Understand Azure networking components (VNet, NSG, Public IP)

Install and configure NGINX

Expose a web service securely

Apply cost management best practices

🏗 Azure Architecture Components

The following resources were deployed inside a Resource Group:

Virtual Machine (Ubuntu 24.04 LTS)

Virtual Network (VNet)

Subnet

Network Interface (NIC)

Public IP Address

Network Security Group (NSG)

Managed OS Disk

Network Architecture Flow

Client → Public IP → NSG → NIC → VM → NGINX Service

🔐 Security Configuration

Authentication method: SSH Public Key (.pem file)

Password authentication avoided

NSG inbound rules configured:

TCP 22 (SSH)

TCP 80 (HTTP)

VM exposed only required ports

VM stopped (deallocated) after testing to prevent unnecessary cost

Security considerations:

Principle of least privilege

Minimal attack surface exposure

Public IP awareness

Secure remote access configuration

⚙️ Deployment Process
1️⃣ Virtual Machine Creation

Region: Switzerland North

Image: Ubuntu Server 24.04 LTS

Size: Standard D2s_v3

Authentication: SSH Key

Public IP assigned

2️⃣ SSH Connection
ssh -i vm-lab03-linux_key.pem azureuser@<public-ip>

3️⃣ Install NGINX Web Server
sudo apt update
sudo apt install nginx -y
sudo systemctl status nginx


Service status confirmed as:

active (running)

4️⃣ Public Web Access Test

Accessed:

http://<public-ip>

Successfully displayed:

Welcome to nginx!

🧠 Key Learning Outcomes

Practical understanding of Azure IaaS

VM deployment lifecycle

Azure networking fundamentals

NSG configuration and traffic control

SSH key-based authentication

Linux service management

Public vs private IP addressing

Basic cloud security posture

💰 Cost Management

The VM was deallocated after testing to avoid compute charges.

Understanding Azure billing behavior is critical when working in cloud environments.

📸 Evidence

Screenshots included in the /images folder:

VM Overview

Networking configuration

NSG inbound rules

SSH terminal session

NGINX public webpage

📈 Professional Relevance

This lab simulates a real-world scenario where infrastructure must be deployed, secured, and validated in a cloud environment.

Skills demonstrated align with:

Cloud Engineer roles

DevOps positions

Entry-level Cloud Security roles

Azure Fundamentals certification preparation
