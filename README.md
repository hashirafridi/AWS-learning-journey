# ☁️ AWS Learning Journey — Lesson 1: 🚀 Creating My First EC2 Instance

Welcome to my **AWS Cloud Journey** 🌍  
This is my first hands-on step into the world of **Amazon Web Services (AWS)** — launching, configuring, and connecting to my very first **EC2 Instance** (a virtual server).

---

## 🎯 Objective
Learn how to:
- 🧩 Launch a free-tier EC2 instance  
- 🔐 Create and use key pairs securely  
- 🧑‍💻 Connect to the instance via AWS Console and SSH

---

## ⚙️ Step-by-Step Guide

### 🪪 Step 1: Give the Instance a Name
- Go to the **EC2 Dashboard → Launch Instance**
- Enter a clear name, e.g. `my-first-ec2-instance`

---

### 💿 Step 2: Choose an Operating System (AMI)
- Select an **Amazon Machine Image (AMI)**  
  Example: **Ubuntu Server 24.04 LTS (Free tier eligible)**
- This defines what OS your instance will run.

---

### ⚡ Step 3: Choose an Instance Type
- Select **t2.micro** — free-tier eligible (1 vCPU, 1GB RAM)
- Perfect for beginners and lightweight practice.

---

### 🔑 Step 4: Create a Key Pair
Key pairs are used to securely connect to your instance.

- Click **Create new key pair**
- **Key pair type:** RSA  
- **Private key format:** `.pem` (for SSH via Git Bash / macOS / Linux)

When you create the key pair:
- AWS keeps the **public key** 🗝️ (stored on the server)
- You keep the **private key** 🔒 (`.pem` file)

💡 *Think of it as a lock and key system — AWS has the lock, and you have the only key.*

---

### 🧾 Step 5: Name Your Key Pair
- Example name: `hashir-key`
- Download and store your `.pem` file safely — you’ll need it for SSH.

---

### 🌐 Step 6: Configure Network Settings
- Choose **Create Security Group**
- Allow the following inbound rule:
  - ✅ **SSH (Port 22)** — *Allow from Anywhere (0.0.0.0/0)*  
    ⚠️ *For learning only — never do this in production!*

---

### 🚀 Step 7: Launch the Instance
- Review all settings
- Click **Launch Instance**
- Wait a few seconds — your virtual server is now alive in the AWS Cloud! 🌤️

---

## 🔗 Step 8: Connect to the Instance

### 🌩️ Option 1: Using AWS Console
- Click **Connect → EC2 Instance Connect**
- Opens a web-based SSH terminal right in your browser.

---

### 💻 Option 2: Using SSH via Git Bash (Recommended)
1. Move your `.pem` key to a secure folder (e.g. `C:\aws-keys`)
2. Open **Git Bash** in that folder
3. Run these commands:

```bash
# Set correct file permissions
chmod 400 hashir.pem

# Connect to your EC2 instance
ssh -i "hashir.pem" ubuntu@ec2-54-145-50-224.compute-1.amazonaws.com
```

✅ You’re now inside your virtual server — your first step as a cloud engineer!

---

## 🧩 Notes & Learnings
- This is a **basic setup** for practice.
- In upcoming lessons, we’ll explore:
  - 🕸️ Custom VPC & Subnets
  - 🛡️ Security Groups in detail
  - 🌍 Elastic IPs and DNS setup
  - 🌐 Deploying a simple web app to EC2

---

## 🏁 Summary
You have successfully:
- ✅ Launched your first EC2 instance  
- ✅ Created and used a key pair securely  
- ✅ Connected via both AWS Console and SSH  

🎉 Congratulations on completing Lesson 1!

---

## 💡 Next Steps
- Learn about **Elastic IPs**  
- Understand **Security Groups** deeper  
- Deploy your first simple **website on EC2**  

---

### ✍️ Author
**Hashir Afridi**  
📘 *AWS Beginner — Documenting my cloud learning journey one step at a time.*

---

### 🗂️ Repository Structure (for Future Lessons)
```
aws-learning-journey/
│
├── README.md               # Overview of your journey
├── ec2-basics/
│   └── README.md           # Lesson 1 (this file)
├── vpc-basics/
│   └── README.md
├── s3-bucket-setup/
│   └── README.md
└── lambda-functions/
    └── README.md
```

🌟 *Stay tuned for the next chapter — "Understanding VPC & Networking in AWS!"*
