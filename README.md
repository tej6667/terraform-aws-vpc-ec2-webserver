# 🚀 Deploy a Secure EC2 Web Server with Terraform, VPC, and Remote State on AWS

Are you looking to automate your AWS infrastructure and deploy a web server with best practices? In this guide, you'll learn how to use Terraform to:

- Provision a secure VPC with public/private subnets
- Launch an EC2 instance running Apache with a sample website
- Manage SSH keys and security groups
- Store your Terraform state remotely in S3 for safety and collaboration

Let's get started!

---

## 🗂️ Project Structure

```
.
├── backend.tf
├── Instance.tf
├── KeyPair.tf
├── Provider.tf
├── README.md
├── SecurityGroup.tf
├── vars.tf
├── vpc.tf
├── web.sh
├── .gitignore
├── terraform-vpc-ssh-key
├── terraform-vpc-ssh-key.pub
└── .terraform/
```

---

## 📦 What Does This Project Do?

- **Creates a VPC** with public and private subnets across multiple Availability Zones
- **Sets up an Internet Gateway** and routing for public subnets
- **Launches an EC2 instance** in a public subnet
- **Configures a Security Group** for SSH and HTTP access
- **Manages SSH Key Pairs** for secure access
- **Provisions Apache Web Server** with a sample website using a shell script
- **Stores Terraform state remotely** in an S3 bucket for collaboration and safety

---

## 🛠️ Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) installed
- [AWS CLI](https://aws.amazon.com/cli/) installed and configured (`aws configure`)
- An AWS account with permissions to create EC2, VPC, and S3 resources

---

## 📁 File Overview

- **Provider.tf**: AWS provider configuration
- **vpc.tf**: VPC, subnets, internet gateway, and route tables
- **Instance.tf**: EC2 instance definition and provisioning
- **KeyPair.tf**: SSH key pair resource
- **SecurityGroup.tf**: Security group for SSH/HTTP access
- **vars.tf**: Variables for region, AMI, zones, etc.
- **backend.tf**: Remote state backend (S3)
- **web.sh**: Script to install Apache and deploy a sample website
- **.gitignore**: Ignore sensitive files and Terraform state
- **terraform-vpc-ssh-key / .pub**: SSH keys (do not commit private key!)

---

## 🚦 Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/your-username/terraform-ec2-web-s3.git
cd terraform-ec2-web-s3

# 2. Initialize Terraform
terraform init

# 3. Review the plan
terraform plan

# 4. Apply the configuration
terraform apply
# Type 'yes' when prompted

# 5. Destroy resources when done
terraform destroy
# Type 'yes' when prompted
```

---

## ⚙️ Customization

- **Region & Zones:** Edit `vars.tf` for your preferred AWS region and availability zones.
- **AMI:** Update the `amiID` map in `vars.tf` for your region.
- **Security Group:** Change allowed IPs in `SecurityGroup.tf`.
- **S3 Backend:** Set your S3 bucket name in `backend.tf`.
- **SSH Key:** Replace with your own key in `KeyPair.tf` and upload your public key.

---

## 📝 Notes & Best Practices

- **Never commit AWS credentials or private keys.**
- **Review security group rules before applying.**
- **Remote state in S3 is critical for team collaboration and disaster recovery.**
- **Remember to destroy resources to avoid AWS charges.**

---

## 🧩 Learn More

- [Terraform Documentation](https://www.terraform.io/docs)
- [AWS VPC Documentation](https://docs.aws.amazon.com/vpc/)
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)

---

## 💬 Questions?

Drop a comment below or check out the [GitHub repo](https://github.com/your-username/terraform-ec2-web-s3) for more details!

---

Happy automating! 🚀



