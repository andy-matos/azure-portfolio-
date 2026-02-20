🚀 Lab 03 – Deploying a Linux Virtual Machine in Microsoft Azure
📌 Objective

Deploy a Linux Virtual Machine in Microsoft Azure, configure secure remote access using SSH key authentication, install a web server (NGINX), and publish a public web page accessible over the internet.

🏗 Architecture Overview

This lab includes the following Azure resources:

Virtual Machine (Ubuntu 24.04 LTS)

Virtual Network (VNet)

Subnet

Network Interface (NIC)

Public IP Address

Network Security Group (NSG)

Managed OS Disk

The VM was deployed inside a Virtual Network with a public IP assigned for internet access.

⚙️ Technologies Used

Microsoft Azure Portal

Ubuntu Server 24.04 LTS

SSH Key Authentication

Network Security Groups (NSG)

NGINX Web Server

🔐 Security Configuration

SSH access configured using a private key (.pem)

Password authentication disabled

NSG inbound rule created to allow:

Port 22 (SSH)

Port 80 (HTTP)

Public access controlled through Azure NSG

🖥 Deployment Steps
1️⃣ Create Virtual Machine

Region: Switzerland North

Image: Ubuntu Server 24.04 LTS

Authentication type: SSH public key

VM Size: Standard D2s v3

2️⃣ Configure Networking

Created Virtual Network automatically

Assigned Public IP

Configured NSG inbound rules:

Allow SSH (22)

Allow HTTP (80)

3️⃣ Connect via SSH
ssh -i vm-lab03-linux_key.pem azureuser@<public-ip>

4️⃣ Install NGINX
sudo apt update
sudo apt install nginx -y
sudo systemctl status nginx

5️⃣ Verify Web Server

Accessed:

http://<public-ip>


Successfully displayed:

"Welcome to nginx!"

🌐 Network Flow Explanation

Client connects to Public IP.

Traffic passes through Network Security Group.

NSG allows port 80.

Request reaches VM.

NGINX responds with web page.

🧠 Key Learning Outcomes

Understanding Azure IaaS architecture

Deploying and configuring Linux VMs

Managing NSG inbound rules

Working with SSH key authentication

Publishing services securely to the internet

Understanding public vs private IP addressing

💰 Cost Management

📸 Evidence

Screenshots included in the /images folder:

VM Overview

NSG Inbound Rule configuration

SSH terminal connection

NGINX running

Public webpage

📈 Professional Impact

This lab demonstrates practical experience with Azure Infrastructure as a Service (IaaS), networking, security configuration, and Linux server management.

The VM was stopped (deallocated) after testing to prevent unnecessary compute charges.
