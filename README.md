# AWS IAM Roles and Policies with Terraform

This project demonstrates how to provision and manage AWS Identity and Access Management (IAM) roles, customer-managed policies, and EC2 instance profiles using Terraform following the principle of least privilege.

## 🏗️ Core Architectural Components

Rather than using long-term static credentials, this configuration automates secure access delegation using:
* **Custom IAM Policy:** Grants scoped read and write permissions (`s3:GetObject`, `s3:PutObject`, `s3:ListBucket`) to a targeted S3 bucket.
* **IAM Execution Role:** Configured with an assume-role trust policy allowing EC2 instances to retrieve credentials dynamically.
* **Role Attachment & Instance Profile:** Attaches the scoped policy to the role and binds it to compute resources.

## 📂 Project Structure

* `main.tf` - Single consolidated configuration file containing the AWS provider, variables, IAM policy document, IAM role, and policy attachments.

## 🚀 Deployment Workflow

1. **Initialize the working directory:**
   ```bash
   terraform init
   terraform plan
   terraform apply -auto-approve
   
