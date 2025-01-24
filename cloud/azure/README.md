# Cloud Computing Fundamentals

## Table of Contents
- [What is the Cloud?](#what-is-the-cloud)
- [Cloud Service Models](#cloud-service-models)
- [Understanding Virtual Networks (VNet) and Subnets](#understanding-virtual-networks-vnet-and-subnets)
- [Planning and Creating a Virtual Network in Azure](#planning-and-creating-a-virtual-network-in-azure)
- [Creating a Virtual Machine in Azure](#creating-a-virtual-machine-in-azure)
- [Deleting Azure Resources](#deleting-azure-resources)
- [Generating an RSA Key Pair](#generating-an-rsa-key-pair)
- [Azure Usage Guidelines](#azure-usage-guidelines)

---

# What is the Cloud?

## Definition
- **Centrally Managed**: Resources are managed/monitored by a central authority
- **Service Available Over the Internet**: Accessible from anywhere with internet connectivity

## Key Components
- **VMs (Virtual Machines)**: Compute resources for running applications
- **VNet (Virtual Network)**: Secure network infrastructure connecting resources
- **DBs (Databases)**: Structured data storage systems
- **Storage**: File storage services (e.g., AWS S3, Azure Blob Storage)

## Key Concept
The cloud provides scalable infrastructure for efficient resource management and deployment.

---

# Cloud Service Models

## Deployment Options
- **On-Premises**: Full responsibility for hardware, software, and data
- **Cloud Models**:
  - **IaaS (Infrastructure as a Service)**: Manage applications/data; provider handles infrastructure
  - **PaaS (Platform as a Service)**: Focus on applications; provider manages platform
  - **SaaS (Software as a Service)**: Fully managed software solutions

## Responsibility Shift
- Moving from On-Premises → SaaS reduces user management while increasing provider responsibility

---

# Understanding Virtual Networks (VNet) and Subnets

## Virtual Network (VNet)
- **Analogy**: Digital apartment building providing secure space for resources
- **CIDR Block**: Defines IP address range (e.g., `10.0.0.0/16` = ~65,000 IPs)

## Subnets
- **Analogy**: Rooms within the apartment (VNet)
- **Subnet CIDR**: Divides VNet space (e.g., `10.0.2.0/24` = 256 IPs)

### Example Configuration
| Component        | CIDR Block       | Capacity  |
|------------------|------------------|-----------|
| VNet             | `10.0.0.0/16`    | 65,536 IPs|
| Public Subnet    | `10.0.2.0/24`    | 256 IPs   |
| Private Subnet   | `10.0.3.0/24`    | 256 IPs   |

---

# Planning and Creating a Virtual Network in Azure

## Planning Steps
1. **Naming**: `tech501-[your_name]-2-subnet-vnet`
2. **CIDR Block**: `10.0.0.0/16`
3. **Subnets**:
   - Public: `10.0.2.0/24`
   - Private: `10.0.3.0/24`

## Creation Process
1. **Project Setup**
   - Select subscription & resource group
2. **Instance Configuration**
   - Name: `tech501-[your_name]-vnet`
   - Region: UK South
3. **Networking**
   - Address space: `10.0.0.0/16`
   - Tags: `owner: [Your_Name]`

---

# Creating a Virtual Machine in Azure

## VM Specifications
- **Name**: `tech501-[your_name]-first-vm`
- **Region**: UK South
- **Security**: Standard
- **Image**: Ubuntu Pro 18.04 LTS Gen2
- **Size**: Standard_B1s (1 vCPU, 1 GiB RAM)
- **Admin**: `adminuser`
- **SSH**: Use existing Azure-stored key pair

## Configuration Steps
1. **Basic Settings**
   - Allow HTTP & SSH inbound ports
2. **Disks**
   - OS Disk Type: Standard SSD
3. **Networking**
   - Virtual Network: `tech501-[your_name]-vnet`
   - Subnet: `public-subnet`
   - Enable "Delete public IP and NIC when VM is deleted"

## Connection Guide
# Connect via SSH
ssh -i ~/.ssh/[your_key].pem adminuser@[vm-public-ip]
# Verify connection
pwd

# Managing Azure Resources

## Deleting Virtual Machines

### Cleanup Process
1. **Navigate to Resources**
   - Portal Home → Resource Groups → `tech501`
   - Use name filter to locate target resources

2. **Resources to Delete**
   ```markdown
   - Virtual Machine
   - OS Disk & Data Disks
   - Network Interface
   - Public IP Address
   - Network Security Group (if unused)

---

# Generating an RSA Key Pair

## What is an RSA Key Pair?
An RSA key pair is used for secure communication, such as connecting to servers via SSH. It consists of:
- A **private key** (kept secure by you).
- A **public key** (shared with others to grant access).

## Commands to create public and private keys for Azure
* Create .ssh directory with `mkdir .ssh` (if it doesn't exist)
* Use `ls -a` to check if .ssh directory was created successfully
* Navigate into .ssh with `cd .ssh`
* Verify current location with `pwd` (print working directory)
* Generate SSH key pair using:

  ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
 
  This creates a public and private key pair
* Enter file in which to save the key (/c/Users/intel/.ssh/id_rsa): tech501-haashim-az-key
* Verify keys were created with `ls -l`
* Public key will have .pub extension
* Set correct permissions:
  * `chmod 700 ~/.ssh`
  * `chmod 600 ~/.ssh/id_rsa`
  * `chmod 644 ~/.ssh/id_rsa.pub`
* Start SSH agent: `eval $(ssh-agent -s)`
* Add private key: `ssh-add ~/.ssh/id_rsa`

### Azure Rules to Follow

#### Creating a Vnet
- Get approval before making resources
- Add your name as Owner tag on everything
- Only use "UK South" location (Since I'm in London)
- It would be better to use a naming convention, IE: "tech501-haashim-demo-vnet"

#### Using Azure and VMs
- Work between 9am and 5pm
- Ask trainer if you need to work late
- Turn off VMs when:
  - You're not using them
  - Work day ends at 5pm

#### Keeping Things Secure
- Keep .pem files in .ssh folder
- Keep .ssh folder out of Git

#### Cleaning Up
- You must delete resources you don't use
- Check and remove:
  - VMs you don't need
  - Storage you don't use
  - Network stuff you're done with
  - Any other unused Azure items

### Virtual Networking Architecture

#### Underlay Network (Physical Foundation)
- **Physical Structures**
  * Fabric: All physical components required for virtual networking (switches, cables, routers)  
  * TEP (Tunneling Endpoint): Interface where virtual networks connect to physical infrastructure  
  * Routing/Bridges: Hybrid interfaces supporting both virtual and physical environments  
  * No Intelligence: Provides basic connectivity without advanced logic  

#### Overlay Network (Virtual Layer)  
- **Segments**: Isolated Layer 2 network domains  
- **Transport Zones**: Define physical host boundaries for virtual networks  
- **Virtual Routers/Bridges**: Fully software-defined networking components  
- **Micro-Segmentation**: Enables granular security controls through:  
  * Embedded firewalls  
  * Service insertion points  
  * Resource-to-resource isolation policies  
