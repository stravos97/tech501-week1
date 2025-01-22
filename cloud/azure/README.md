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

---

# Generating an RSA Key Pair

## What is an RSA Key Pair?
An RSA key pair is used for secure communication, such as connecting to servers via SSH. It consists of:
- A **private key** (kept secure by you).
- A **public key** (shared with others to grant access).

## Steps to Generate an RSA Key Pair
1. Open your terminal.
2. Run the following command:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "youremailaddress"
   ```
