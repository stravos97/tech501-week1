# What is the Cloud?

## Definition
- **Centrally Managed**: Resources are managed and monitored by a central authority.
- **Service Available Over the Internet**: Users can access services online, no matter where they are.

## Components of the Cloud
- **VMs (Virtual Machines)**: Compute resources to run applications.
- **VNet (Virtual Network)**: Connects resources securely.
- **DBs (Databases)**: Stores and retrieves data.
- **Storage**: For saving files, like AWS S3 or Azure Blob Storage.

## Key Concept
The cloud provides capacity and flexibility to create and manage resources effectively.

---

# Cloud Service Models

## On-Premises vs Cloud
- **On-Premises**: You manage everything, including hardware, software, and data.
- **Cloud Models**:
  - **IaaS (Infrastructure as a Service)**: You manage data and applications; the provider manages the infrastructure.
  - **PaaS (Platform as a Service)**: The provider manages most resources; you focus on applications.
  - **SaaS (Software as a Service)**: The provider manages everything; you use the software.

## Control/Responsibility
- As you move from On-Premises to SaaS, your management decreases, and the provider’s responsibility increases.

---

# Understanding Virtual Networks (VNet) and Subnets

## What is a Virtual Network (VNet)?
- A VNet is like an **apartment**. It provides the overall space to house and connect resources securely.

## What is a Subnet?
- Within the VNet, you have **rooms** (subnets). Each subnet serves a specific purpose and uses part of the total space.

## Addressing the Space
1. The **CIDR Block** defines the size of the "apartment" (e.g., `10.0.0.0/16`, supporting ~65,000 IPs).
2. Each **subnet CIDR block** divides that space into smaller sections (e.g., `10.0.2.0/24` for 256 IPs).

### Example Setup
- VNet CIDR Block: `10.0.0.0/16` (the whole apartment).
- Subnet 1: `10.0.2.0/24` (a room with 256 IPs).
- Subnet 2: `10.0.3.0/24` (another room with 256 IPs).

## Key Takeaways
- The VNet provides the structure and connectivity (like the apartment walls).
- Subnets divide the space for organization and management (like rooms in the apartment).

---

# Planning and Creating a Virtual Network in Azure

## Steps to Plan a VNet
1. **Define VNet Name**: For example, `tech501-ramon-2-subnet-vnet`.
2. **CIDR Block**: Specify the IP range, e.g., `10.0.0.0/16` (supports ~65,000 IPs).
3. **Subnets**:
   - Public Subnet: `10.0.2.0/24` (256 IPs).
   - Private Subnet: `10.0.3.0/24` (256 IPs).

## Creating a VNet in Azure
1. **Project Details**: Select the subscription and resource group.
2. **Instance Details**: Define the VNet name and region.
3. **IP Addresses**: Allocate the address space.
4. **Tags**: Add metadata (e.g., owner: `Haashim`).

### Finalizing
- Review and create the VNet.
- Set up subnets and assign resources as needed.


### instructions for creating VM:

Our virtual machine:
Name: tech501-your_name-first-vm
Region: UK South
Security: standard
Image (i.e. the OS that will go onto the machine): Ubuntu Pro 18.04 LTS Gen 2 [LTS means long term support for ~7 years]
Size: Standard_B1s — 1 vcpu, 1 GiB [very important to set correctly because this impacts pricing]
Administrator account: adminuser
Use existing key pair stored in Azure (use the one with your name)
Select inbound ports: allow HTTP and SSH traffic
Disks tab:
OS disk type: Standard SSD
Networking tab:
Virtual network: your named version
Subnet: public-subnet
Choose Delete public IP and NIC when VM is deleted option

conect > select nateive ssh > start

fill in window:
- provide ssh key path
- use provided code
- paste into terminal,say 'yes' if asked permissions
- can check that you are in the vm by running a command such as pwd

### deleting vm

home > resouce group > tech501
filter for name
delete: disk, network interface group, maybe the network security key, public IP, VM itself
keep: virtual network + ssh group


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
