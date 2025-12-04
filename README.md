# AWS EC2 IAM Role for S3 Access

## 📌 Overview
This project demonstrates how to configure an **IAM role** that allows an **EC2 instance** to securely access an **S3 bucket** without using access keys.  
Hands-on was performed via the **AWS Management Console**, with CLI verification.

---

## 🔹 Steps

### 1. Create IAM Role
- Go to **IAM → Roles → Create role**
- Trusted entity: **AWS service**
- Use case: **EC2**
- Attach policy: `AmazonS3FullAccess` (or custom policy)
- Role name: `EC2S3AccessRole`

### 2. Attach Role to EC2
- Go to **EC2 → Instances**
- Select instance → **Actions → Security → Modify IAM Role**
- Choose `EC2S3AccessRole`

### 3. Verify from EC2
SSH into EC2 and run:
```bash
aws s3 ls
