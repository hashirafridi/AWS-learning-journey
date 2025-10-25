☁️ AWS Journey — Lesson 1: Creating My First EC2 Instance

Welcome to my AWS learning journey!
This is my first step into Amazon Web Services — creating and connecting to a virtual server (EC2 Instance).

🧠 Objective

Learn how to:

Launch a free-tier EC2 instance

Configure security and key pairs

Connect to the instance using AWS console and SSH

⚙️ Step-by-Step Guide
Step 1: Give the Instance a Name

Start from the EC2 Dashboard → Launch Instance

Enter a simple and clear name, e.g. my-first-ec2-instance

Step 2: Choose an Operating System (AMI)

Select an Amazon Machine Image (AMI)
Example: Ubuntu Server 24.04 LTS (Free tier eligible)

This defines what OS your instance will run.

Step 3: Choose an Instance Type

Select t2.micro — free-tier eligible (1 vCPU, 1GB RAM)

Suitable for basic learning and testing.

Step 4: Create a Key Pair 🔑

Key pairs are used to securely connect to your instance.

Click Create new key pair

Key pair type: RSA

Private key format: .pem (used for SSH on macOS/Linux/Git Bash)

When you create the key pair:

AWS keeps the public key (stored on the server)

You download the private key (.pem) — used to authenticate your connection

💡 Think of it as a lock and key system — AWS has the lock, and you have the only key.

Step 5: Name Your Key Pair

Give it a clear name like hashir-key

Download the .pem file and keep it safe! (You’ll need it for SSH)

Step 6: Configure Network Settings

Choose Create Security Group

Allow the following inbound rules:

✅ SSH (Port 22) — Allow from Anywhere (0.0.0.0/0)
(For practice only; in production, always limit access to your IP.)

Step 7: Launch the Instance 🚀

Review your settings

Click Launch Instance

Wait a few seconds — your virtual server is now running in AWS Cloud!

🔗 Step 8: Connect to the Instance
Option 1: Using AWS Console

Click Connect → EC2 Instance Connect

This opens a web-based SSH terminal directly in your browser.

Option 2: Using SSH via Git Bash (Recommended)

Move your .pem key to a safe folder (e.g. C:\aws-keys)

Open Git Bash in that folder

Run the following commands:

# Step 1: Set permissions for the key
chmod 400 hashir.pem

# Step 2: Connect to the EC2 instance
ssh -i "hashir.pem" ubuntu@ec2-54-145-50-224.compute-1.amazonaws.com


If connected successfully, your terminal prompt will change — you’re now inside your remote server!

🧩 Common Notes

This is a basic setup for practice.

In future lessons, we’ll dive deeper into:

Custom VPC & Subnets

Security groups in detail

Elastic IPs and DNS setup

Deploying web apps to EC2

🏁 Conclusion

You have successfully:
✅ Launched your first AWS EC2 instance
✅ Created and used key pairs for secure access
✅ Connected via AWS Console and SSH

💡 Next Steps

Learn about Elastic IPs

Understand Security Groups deeper

Practice deploying a simple website on EC2

✍️ Author

Hashir Afridi
AWS Beginner — Learning Cloud, One Step at a Time
