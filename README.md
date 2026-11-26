
<div align="center">

# ☁️ AWS EC2, SSM Tunnels & Private RDS Automation Lab

**Automated Bastion Lifecycle, Zero-Trust Port Forwarding & Private PostgreSQL Access on Linux**

[![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)](https://aws.amazon.com/)
[![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)](https://www.linux.org/)
[![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)](https://www.gnu.org/software/bash/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)

</div>

---

## 🖥️ Architecture & Animated Workflow

<div align="center">

https://github.com/user-attachments/assets/0223a20e-6928-4f7e-a533-3d356cdf7605


</div>

Practical cloud infrastructure and automation lab built on a Linux environment, implementing **Zero-Trust** access and **FinOps** cost control on AWS. Modular Bash scripts (`01-zip.sh`, `02-unzip.sh`, `05-1-criar-tunel-propria-ec2.sh`, `05-2-criar-tunel-rds.sh`, `06-1-ligar-porteiro.sh`, and `06-2-parar-porteiro.sh`) orchestrate the on-demand lifecycle of an EC2 Bastion host and establish encrypted **AWS Systems Manager (SSM)** port-forwarding tunnels — completely eliminating SSH keys and public database exposure.

---

## 📄 Complete Technical Documentation

For the full step-by-step technical guide, objectives, architecture breakdown, and validation walkthrough, access the complete PDF document:

📘 **[Download / View Complete Technical Material (PDF)](./docs/ws-ec2-ssm-rds-bash-automation.pdf)**

---

## 🛠️ Technologies & Tools

* **Cloud Infrastructure:** Amazon EC2 (Bastion Host & Docker Server), Amazon RDS (Private PostgreSQL 18.3), AWS Systems Manager (SSM Port Forwarding), Amazon VPC & Security Groups (`bia-db`), AWS IAM
* **Operating System & Automation:** Linux, Bash / Shell Scripting, AWS CLI v2, AWS Session Manager Plugin
* **Containers & Database Administration:** Docker, Docker Compose, DBeaver (PostgreSQL JDBC)
* **Version Control & IDE:** Git, GitHub, Visual Studio Code

---

## 🧪 Execution & Validation Evidence

| Packaging Automation (Bash) | EC2 Bastion Lifecycle & SSM Tunnel |
| :---: | :---: |
| ![Bash Zip and Unzip Automation](./image/1-bash-zip-unzip-automation.jpeg) | ![EC2 Bastion Start Stop and SSM Tunnel](./image/04-ec2-bastion-lifecycle-ssm-tunnel.jpeg) |
| *Shell scripts (`01-zip.sh` & `02-unzip.sh`) packaging the BIA app into `bia.zip` and extracting a clean copy into `bia2`.* | *Bash + AWS CLI scripts stopping and starting the `bia-dev` EC2 on demand (FinOps) and opening the SSM tunnel on port `3002`.* |

| Private Amazon RDS via DBeaver (Port 5433) | BIA Web App via Local Tunnel (Port 3002) |
| :---: | :---: |
| ![DBeaver Connected to RDS PostgreSQL](./image/03-dbeaver-rds-postgresql-connection.jpeg) | ![BIA Web App Running on Localhost 3002](./image/02-bia-webapp-localhost-3002.jpeg) |
| *Successful DBeaver connection to the private Amazon RDS PostgreSQL 18.3 database at `localhost:5433` via SSM bridge.* | *BIA web application running locally at `localhost:3002` through the SSM tunnel (`3002 → 3001`) without public EC2 exposure.* |
