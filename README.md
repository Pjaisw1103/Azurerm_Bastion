# 🌐 Azure Infrastructure Automation with Terraform

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=240&text=Azure%20Infrastructure%20Automation&fontSize=40&fontAlignY=40&desc=Terraform%20%7C%20Azure%20%7C%20Modular%20Infrastructure&descAlignY=60&fontColor=ffffff&animation=fadeIn&color=0:0078D4,50:623CE4,100:0D1117"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Terraform-623CE4?style=for-the-badge&logo=terraform&logoColor=white"/>
  <img src="https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white"/>
  <img src="https://img.shields.io/badge/IaC-Infrastructure%20as%20Code-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Production%20Ready-22C55E?style=for-the-badge"/>
</p>

---

## 📌 Overview

This project automates the deployment of a complete Azure infrastructure using Terraform modules.

The architecture follows Infrastructure as Code (IaC) principles and demonstrates how to provision networking, compute, database, and secure access resources in a reusable and scalable manner.

### Resources Provisioned

* Resource Group
* Virtual Network
* Subnets
* Public IP
* Virtual Machine
* Azure Bastion
* Azure SQL Server
* Azure SQL Database

---

## 🏗️ Architecture

```text
Azure Cloud
│
├── Resource Group
│
├── Virtual Network
│   └── Subnets
│
├── Public IP
│
├── Virtual Machine
│
├── Azure Bastion
│
└── Azure SQL
    ├── SQL Server
    └── SQL Database
```

---

## ✨ Key Features

| Feature                   | Description                            |
| ------------------------- | -------------------------------------- |
| ☁️ Azure Infrastructure   | Complete cloud resource provisioning   |
| 🏗️ Modular Design        | Independent reusable Terraform modules |
| 🔐 Secure Access          | Azure Bastion for VM connectivity      |
| 💻 Compute Resources      | Azure Virtual Machines                 |
| 🗄️ Database Layer        | Azure SQL Server & Database            |
| 🔄 Infrastructure as Code | Automated deployments with Terraform   |

---

## 📊 Infrastructure Components

| Service         | Purpose                        |
| --------------- | ------------------------------ |
| Resource Group  | Resource organization          |
| Virtual Network | Network isolation              |
| Subnets         | Segmented network architecture |
| Public IP       | External connectivity          |
| Virtual Machine | Compute workload               |
| Azure Bastion   | Secure RDP/SSH access          |
| SQL Server      | Managed database service       |
| SQL Database    | Application data storage       |

---

## 📂 Repository Structure

```text
.
├── Environment/
│   ├── main.tf
│   └── provider.tf
│
├── Module/
│   ├── azurerm_resource_group/
│   ├── azurerm_virtual_network/
│   ├── azurerm_subnet/
│   ├── azurerm_public_ip/
│   ├── azurerm_virtual_machine/
│   ├── azurerm_bastion/
│   ├── azurerm_mssql_server/
│   └── azurerm_mssql_database/
│
└── README.md
```

---

## 🛠️ Technology Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=terraform,azure,git,github,vscode"/>
</p>

---

## 🚀 Deployment Steps

### Clone Repository

```bash
git clone <repository-url>
cd Environment
```

### Initialize Terraform

```bash
terraform init
```

### Validate Configuration

```bash
terraform validate
```

### Generate Execution Plan

```bash
terraform plan
```

### Deploy Infrastructure

```bash
terraform apply -auto-approve
```

---

## 🔐 Azure Bastion Benefits

Azure Bastion provides secure browser-based access to Azure Virtual Machines without exposing public IP addresses.

### Advantages

* No public IP on VMs
* Secure RDP & SSH connectivity
* Azure Portal integration
* Reduced attack surface
* Managed Azure service

---

## 📜 Prerequisites

Before deploying this project:

* Terraform v1.5+
* Azure CLI installed
* Active Azure Subscription
* Authenticated Azure account

```bash
az login
```

---

## 💡 Best Practices Implemented

* Modular Terraform architecture
* Infrastructure as Code (IaC)
* Reusable components
* Secure VM access through Bastion
* Resource isolation using VNets and Subnets
* Consistent resource deployment

---

## 📈 Learning Outcomes

* Terraform Module Development
* Azure Networking
* Azure Virtual Machines
* Azure Bastion
* Azure SQL Services
* Infrastructure Automation
* Cloud Security Fundamentals

---

## 🎯 Project Highlights

<p align="center">

<img src="https://img.shields.io/badge/Modular-Terraform-623CE4?style=for-the-badge"/>

<img src="https://img.shields.io/badge/Azure-Bastion-0078D4?style=for-the-badge"/>

<img src="https://img.shields.io/badge/Azure-SQL-success?style=for-the-badge"/>

<img src="https://img.shields.io/badge/IaC-Automation-orange?style=for-the-badge"/>

</p>

---

## 👩‍💻 Author

**Priya Jaiswal**

Azure Cloud | DevOps | Terraform

<p align="center">
  <a href="https://github.com/Pjaisw1103">
    <img src="https://img.shields.io/badge/GitHub-Pjaisw1103-181717?style=for-the-badge&logo=github"/>
  </a>

  <a href="https://linkedin.com/in/priya-jaiswal1103">
    <img src="https://img.shields.io/badge/LinkedIn-Priya%20Jaiswal-0078D4?style=for-the-badge&logo=linkedin"/>
  </a>
</p>

---

<p align="center">
⭐ If you found this project useful, consider giving it a star.
</p>
