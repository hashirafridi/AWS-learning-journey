# ☁️ AWS Learning Journey — Lesson 2: 🌐 Deploying a Simple Website on EC2 with NGINX

Welcome back to my AWS learning journey!  
In this second lesson, I’ll take what I learned in Lesson 1 and go a step further — by **hosting a simple HTML website** on an EC2 instance using **NGINX**. 🚀

---

## 🎯 Objective
Learn how to:
- ⚙️ Launch a new EC2 instance (with HTTP & HTTPS access)
- 🧑‍💻 Connect to the instance using SSH
- 🔄 Install & start NGINX web server
- 🌍 Deploy a basic HTML website

---

## ⚙️ Step-by-Step Guide

### 🪪 Step 1: Launch a New EC2 Instance
We’ll follow the same process as in Lesson 1 — but with a few updates.

1. Go to the **EC2 Dashboard → Launch Instance**
2. **Name:** `web-server-instance`
3. **Operating System (AMI):** Ubuntu Server 24.04 LTS (Free tier eligible)
4. **Instance Type:** t2.micro (Free tier)
5. **Key Pair:** Use the same key from Lesson 1 or create a new one.

---

### 🌐 Step 2: Configure Network Settings
In the **Network Settings** section, do the following:

- Select **Create Security Group**
- Allow the following inbound rules:

| Type | Protocol | Port Range | Source | Purpose |
|------|-----------|-------------|---------|----------|
| SSH | TCP | 22 | 0.0.0.0/0 | Secure remote access |
| HTTP | TCP | 80 | 0.0.0.0/0 | Allow non-secure web traffic |
| HTTPS | TCP | 443 | 0.0.0.0/0 | Allow secure web traffic |

💡 *HTTP is used for normal web traffic, and HTTPS is used for encrypted traffic.*

---

### 🚀 Step 3: Launch the Instance
- Click **Launch Instance**
- Wait until the instance status shows **Running** ✅

---

## 🔗 Step 4: Connect to the Instance via SSH

1. Open **Git Bash** (or your preferred terminal)
2. Navigate to the folder containing your `.pem` file
3. Run the following commands:

```bash
chmod 400 hashir.pem
ssh -i "hashir.pem" ubuntu@<your-ec2-public-dns>
```

Example:
```bash
ssh -i "hashir.pem" ubuntu@ec2-54-145-50-224.compute-1.amazonaws.com
```

---

## ⚙️ Step 5: Update and Install NGINX

Once connected to your EC2 instance:

```bash
# Update package list
sudo apt-get update

# Install NGINX web server
sudo apt-get install nginx -y
```

After installation, check NGINX status:

```bash
sudo systemctl status nginx
```

✅ If you see “active (running)”, it means NGINX is up and working!

---

## 🧱 Step 6: Clone a Repository Containing HTML Files

We’ll clone a simple repo (you can use your own GitHub repo).

```bash
git clone https://github.com/<your-username>/<your-repo>.git
```

Navigate into the cloned directory and check the HTML file:

```bash
cd <your-repo>
ls
```

---

## 📂 Step 7: Copy HTML File to Web Directory

Copy your HTML file to NGINX’s default web directory:

```bash
sudo cp index.html /var/www/html
```

This replaces the default NGINX welcome page with your own website.

---

## 🌍 Step 8: Access Your Website

1. Go to your **EC2 Dashboard**
2. Copy the **IPv4 Public Address** of your instance
3. Paste it into your browser — for example:

```
http://3.85.100.25
```

🎉 You should now see your HTML website live on the internet!

---

## 🧠 What We Learned
- How to allow HTTP/HTTPS traffic in a security group  
- How to install and verify NGINX on an EC2 instance  
- How to deploy a static website using the NGINX web server  

---

## 🏁 Summary
You have successfully:
✅ Launched an EC2 instance for web hosting  
✅ Installed and configured NGINX  
✅ Deployed and viewed your first website on AWS  

---

## 💡 Next Steps
- Learn about **Elastic IPs** for a fixed public IP  
- Understand **Domains & Route 53** for custom URLs  
- Explore **SSL certificates** for HTTPS encryption  

---

### ✍️ Author
**Hashir Afridi**  
📘 *AWS Beginner — Lesson 2: Hosting with EC2 and NGINX*

---

### 🗂️ Repository Structure (Updated)
```
aws-learning-journey/
│
├── README.md
├── ec2-basics/
│   └── README.md
├── web-server-nginx/
│   └── README.md   # ← This lesson
├── vpc-basics/
│   └── README.md
└── s3-bucket-setup/
    └── README.md
```
