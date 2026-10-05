# Azure Infrastructure Automation with Terraform

A modular Terraform configuration for provisioning secure, scalable Azure cloud infrastructure. This project automates the deployment of network isolation, virtual machine compute instances, database services, and secure remote management via Azure Bastion.

---

## Table of Contents

- [Architecture Overview](#architecture-overview)
- [Key Features](#key-features)
- [Infrastructure Components](#infrastructure-components)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [Deployment Guide](#deployment-guide)
- [Security Features](#security-features)
- [Author](#author)

---

## Architecture Overview

```text
                               ┌──────────────────────────────────────────┐
                               │            Azure Resource Group          │
                               │                (rg-demo)                 │
                               └────────────────────┬─────────────────────┘
                                                    │
                 ┌──────────────────────────────────┴──────────────────────────────────┐
                 │                                                                     │
                 ▼                                                                     ▼
    ┌─────────────────────────┐                                           ┌─────────────────────────┐
    │     Virtual Network     │                                           │    Azure SQL Services   │
    │      (vnet-infra)       │                                           │                         │
    └────────────┬────────────┘                                           ├─────────────────────────┤
                 │                                                        │ • MSSQL Server          │
        ┌────────┴────────────────────────┐                               │   (infra-server)        │
        │                                 │                               │                         │
        ▼                                 ▼                               │ • MSSQL Database        │
┌───────────────┐                 ┌───────────────┐                       │   (infra-database)      │
│     Subnet    │                 │ Azure Bastion │                       └─────────────────────────┘
│(subnet-front) │                 │    Subnet     │
└───────┬───────┘                 └───────┬───────┘
        │                                 │
        ▼                                 ▼
┌───────────────┐                 ┌───────────────┐
│ Virtual       │                 │ Azure Bastion │ ◄── Public IP
│ Machines      │                 │ (demo-bastion)│     (pip-bastion)
│ (vm01, vm02)  │                 └───────────────┘
└───────────────┘
```

---

## Key Features

- **Modular Architecture**: Built with reusable and independent Terraform modules under `Module/`.
- **Zero-Public-IP VMs**: Compute workloads are completely isolated within internal subnets.
- **Secure Access**: Native Azure Bastion deployment for SSH/RDP connectivity without exposed public IP addresses.
- **Database Provisioning**: Automated Azure MSSQL Server and Database setup.
- **Scalable Design**: Easily extendable structure to add additional VM nodes or subnets.

---

## Infrastructure Components

| Resource Module | Module Source | Description |
| :--- | :--- | :--- |
| **Resource Group** | `Module/azurerm_resource_group` | Central logical container for all Azure deployment resources |
| **Virtual Network** | `Module/azurerm_virtual_network` | Primary private network boundary (`vnet-infra`) |
| **Subnets** | `Module/azurerm_subnet` | Workload subnet (`subnet-frontend`) and `AzureBastionSubnet` |
| **Public IP** | `Module/azurerm_public_ip` | Dedicated Public IP assigned exclusively to Azure Bastion |
| **Virtual Machines** | `Module/azurerm_virtual_machine` | Virtual machine compute instances (`vm01`, `vm02`) |
| **Azure Bastion** | `Module/azurerm_bastion` | PaaS Bastion host for secure browser-based remote access |
| **MSSQL Server** | `Module/azurerm_mssql_server` | Fully managed Azure SQL database server instance |
| **MSSQL Database** | `Module/azurerm_mssql_database` | Relational SQL database hosted within the SQL Server |

---

## Repository Structure

```text
.
├── Environment/
│   ├── main.tf          # Core infrastructure deployment configuration
│   └── provider.tf      # AzureRM provider configuration & required versions
│
├── Module/
│   ├── azurerm_bastion/          # Azure Bastion module
│   ├── azurerm_mssql_database/   # Azure SQL Database module
│   ├── azurerm_mssql_server/     # Azure SQL Server module
│   ├── azurerm_public_ip/        # Public IP module
│   ├── azurerm_resource_group/   # Resource Group module
│   ├── azurerm_subnet/           # Subnet module
│   ├── azurerm_virtual_machine/  # Virtual Machine module
│   └── azurerm_virtual_network/  # Virtual Network module
│
└── README.md
```

---

## Prerequisites

Ensure you have the following installed and configured before deployment:

1. **Terraform CLI**: Version `v1.5.0` or higher ([Download Terraform](https://developer.hashicorp.com/terraform/downloads))
2. **Azure CLI**: Installed and authenticated ([Download Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli))
3. **Azure Subscription**: Active subscription with permissions to manage resources

Authenticate with your Azure account:

```bash
az login
```

Verify account details:

```bash
az account show
```

---

## Deployment Guide

### Step 1: Clone the Repository

```bash
git clone https://github.com/Pjaisw1103/Azurerm_Bastion.git
cd Azurerm_Bastion/Environment
```

### Step 2: Initialize Terraform

Initialize provider plugins and modules:

```bash
terraform init
```

### Step 3: Validate Configuration

Check syntax and module consistency:

```bash
terraform validate
```

### Step 4: Preview Execution Plan

Review planned resource additions:

```bash
terraform plan
```

### Step 5: Provision Infrastructure

Apply the configuration to deploy resources:

```bash
terraform apply
```

To destroy the deployed infrastructure:

```bash
terraform destroy
```

---

## Security Features

- **PaaS Bastion Management**: Azure Bastion acts as a managed jump host, preventing direct internet access to RDP (3389) or SSH (22) ports.
- **Network Isolation**: Compute workloads reside in isolated internal subnets without public IPs.
- **Explicit Dependencies**: `depends_on` rules enforce structured provisioning order.

---

## Author

**Priya Jaiswal**  
*Azure Cloud & DevOps Engineer*

- GitHub: [@Pjaisw1103](https://github.com/Pjaisw1103)
- LinkedIn: [Priya Jaiswal](https://linkedin.com/in/priya-jaiswal1103)

