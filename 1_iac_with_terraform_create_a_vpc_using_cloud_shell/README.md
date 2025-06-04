# Lab & Activity: Manage IaC with terraform and Create a VPC using Cloud Shell

This folder is part of a simulation in which I act as a Junior Cloud Security Analyst at Cymbal Bank, a fictional international bank undergoing a digital transformation. The tasks included both an **activity** and a **lab**, focused on infrastructure as code (IaC) and network creation.

---

## 🧩 Scenario Overview

Cymbal Bank is adopting a hybrid cloud strategy. As a junior cloud security analyst, I collaborated with the cloud security team to support the secure deployment of infrastructure using Terraform (IaC) and to create a Virtual Private Cloud (VPC) for testing and deployment.

---

## 🔨 Activity: Manage Infrastructure as Code (IaC) with Terraform

In this activity, I evaluated and worked with a basic Terraform configuration to provision cloud resources securely and consistently.

### Key Concepts:
- Infrastructure as Code (IaC)
- Declarative configuration
- Cloud automation

### Example Terraform Configuration:
```hcl
resource "google_compute_network" "vpc_network" {
  name                    = "cymbal-vpc"
  auto_create_subnetworks = false
}
```

*Note: This activity was focused on understanding the configuration and deployment process using Terraform.*

---

## 🧪 Lab: Create a VPC using Google Cloud Shell

This lab involved using the `gcloud` CLI in Google Cloud Shell to manually create a virtual private cloud network and configure basic settings for secure networking.

### Key Steps:
```bash
# Create a custom VPC
gcloud compute networks create cymbal-vpc --subnet-mode=custom

# Create a subnet
gcloud compute networks subnets create cymbal-subnet \
  --network=cymbal-vpc \
  --region=us-central1 \
  --range=10.0.0.0/24



---


## ✅ Outcome

By completing both the activity and the lab, I:
- Gained hands-on experience with IaC principles and Terraform syntax
- Practiced configuring secure cloud networks in GCP
- Strengthened my understanding of cloud automation and networking
