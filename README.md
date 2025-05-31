# Ansible Master-Worker Setup on AWS

This project sets up an Ansible control node (master) and multiple managed nodes (workers) on AWS EC2 instances. It then installs Apache2 on all worker nodes using a sample Ansible playbook.

---

## ✅ Requirements

- AWS account
- SSH key pair (`.pem` file)
- Ubuntu EC2 instances (1 Master, N Workers)
- Security Group with SSH (port 22) open
- Ansible installed on the Master node

---

## 🔧 Steps to Set Up

### 1. 🔐 Launch EC2 Instances

- Launch 1 Ubuntu EC2 instance named `ansible-master`
- Launch 2+ Ubuntu EC2 instances named `ansible-worker1`, `ansible-worker2`, etc.
- Attach same SSH key pair to all
- Place all in the same VPC/subnet if possible

### 2. 🧑‍💻 Connect to Master Node

```bash
ssh -i your-key.pem ubuntu@<master-public-ip>
