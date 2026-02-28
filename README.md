# Zero-Trust DevSecOps Platform on Azure

![Terraform](https://img.shields.io/badge/Terraform-1.6+-purple?logo=terraform)
![Azure](https://img.shields.io/badge/Microsoft%20Azure-Cloud-blue?logo=microsoftazure)
![Security](https://img.shields.io/badge/Security-RBAC%20Monitoring-red)
![IaC](https://img.shields.io/badge/Infrastructure%20as%20Code-Terraform-informational)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Overview

This project demonstrates a Zero-Trust governance and monitoring architecture on Microsoft Azure using Terraform.

It provisions secure infrastructure components and implements security monitoring controls to detect and notify on RBAC (Role-Based Access Control) changes in real-time.

The solution follows Infrastructure-as-Code (IaC) principles and enforces governance using Azure Policy, Azure Monitor, and Activity Log Alerts.

---

## 🏗 Architecture Overview

This architecture detects RBAC role assignment changes and automatically sends email notifications.

### 🔐 Monitoring Flow

1. User performs role assignment change
2. Azure Activity Log captures the event
3. Azure Monitor Activity Log Alert evaluates the event
4. Action Group triggers email notification
5. Security alert is delivered

### 📊 Architecture Diagram

![Azure RBAC Role Assignment Alert Architecture](docs/architecture/azure-rbac-alert-architecture.png)

---

## 🚀 Infrastructure Components

### ✅ Resource Provisioning
- Azure Resource Group
- RBAC Role Assignment (Reader)
- Azure Policy Assignment
- Azure Monitor Alert Rule
- Azure Monitor Action Group

### ✅ Governance Controls
- Built-in Azure Policy: Allowed Locations
- Resource tagging enforcement
- RBAC least-privilege assignment

### ✅ Security Monitoring
- Activity Log Alert on:
  - `Microsoft.Authorization/roleAssignments/write`
  - `Microsoft.Authorization/roleAssignments/delete`
- Email notification via Action Group

---

## 📂 Repository Structure
├── terraform/
│ ├── main.tf
│ └── ...
├── docs/
│ ├── screenshots/
│ └── architecture/
│ └── azure-rbac-alert-architecture.png
├── README.md
└── LICENSE

---

## ⚙️ How to Deploy

### 1️⃣ Clone the repository
```bash
git clone https://github.com/<your-username>/Zero-Trust-DevSecOps-Platform-on-Azure.git
cd Zero-Trust-DevSecOps-Platform-on-Azure/terraform


