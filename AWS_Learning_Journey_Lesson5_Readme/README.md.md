# 🔐 AWS Learning Journey — Lesson 5: Configuring User and Group Permissions in Linux

Welcome to **Lesson 5** of my AWS Learning Journey!  
In this session, I learned to **configure user and group permissions** — an essential part of securing and managing access in cloud-based Linux environments. ☁️🐧

---

## 🎯 **Class Objectives**
By the end of this lesson, I have learned to:
✅ Create and manage users and groups  
✅ Set proper file ownership and permissions  
✅ Secure sensitive files using Linux permissions  
✅ Follow access control best practices  
✅ Simulate enterprise-level permission management  

---

## 🧑‍💻 **Step 1: Check Your Current User**
```bash
whoami
```
🔍 Displays the currently logged-in user.

---

## 👑 **Step 2: Switch to Root User**
```bash
sudo -i
```
⚡ Switches to the **root user** for full administrative privileges.

---

## 🆔 **Step 3: Check User ID and Groups**
```bash
id
```
📋 Displays the user ID (UID), group ID (GID), and all groups the user belongs to.

---

## 👥 **Step 4: Create New Users**
```bash
sudo adduser clouduser
sudo adduser devuser
```
🧩 Creates two users — `clouduser` and `devuser`.

✅ **Verify Users:**
```bash
cat /etc/passwd
grep -i clouduser /etc/passwd
grep -i devuser /etc/passwd
```

---

## 🏗️ **Step 5: Create New Groups**
```bash
sudo groupadd cloudadmin
sudo groupadd devops_team
```
📦 Creates two new groups.

✅ **Verify Groups:**
```bash
cat /etc/group
grep -i cloudadmin /etc/group
grep -i devops_team /etc/group
```

---

## 🧩 **Step 6: Add Users to Groups**
```bash
sudo usermod -aG cloudadmin clouduser
sudo usermod -aG devops_team devuser
```
👥 Adds each user to their respective group.

✅ **Check Group Membership:**
```bash
groups clouduser
groups devuser
```

---

## 📁 **Step 7: Create and Manage a File**
```bash
touch file.txt
```
📝 Creates a new file named `file.txt`.

✅ **Check File Info:**
```bash
ls -l file.txt
```
Shows file owner, group, and permissions.

---

## 👑 **Step 8: Change File Ownership**
```bash
sudo chown clouduser:clouduser file.txt
```
👤 Changes ownership of the file to user `clouduser` and group `clouduser`.

✅ **Verify Ownership:**
```bash
ls -l file.txt
```
**Expected Output:**
```
-rw-r--r-- 1 clouduser clouduser 0 May 10 12:00 file.txt
```

---

## ⚙️ **Step 9: Modify User Permissions**
```bash
chmod u+rwx file.txt
chmod u-w file.txt
```
🔧 Grants full permissions (read, write, execute) to user, then removes write access.

✅ **Verify:**
```bash
ls -l file.txt
```
**Expected Output:**
```
-r-xr--r-- 1 clouduser clouduser 0 May 10 12:00 file.txt
```

---

## 👥 **Step 10: Change Group Ownership & Permissions**
```bash
sudo chown :cloudadmin file.txt
chmod g+rwx file.txt
chmod g-w file.txt
```
👑 Changes the group ownership to `cloudadmin` and adjusts group permissions.

✅ **Verify:**
```bash
ls -l file.txt
```

---

## 🔍 **Step 11: Check Group Information**
```bash
grep -i cloudadmin /etc/group
```
**Expected Output:**
```
cloudadmin:x:1002:devuser
```

---

## 🚫 **Step 12: Remove User from Group**
```bash
sudo gpasswd -d clouduser cloudadmin
```
🧹 Removes `clouduser` from the `cloudadmin` group.

**Expected Output:**
```
Removing user clouduser from group cloudadmin
```

---

## ❌ **Step 13: Delete User and Group**
```bash
sudo userdel clouduser
sudo groupdel cloudadmin
```
🗑️ Deletes both the user and the group.

✅ **Verify Removal:**
```bash
grep -i cloudadmin /etc/group
```

---

## 🔄 **Step 14: Switch Between Users**
```bash
su username
```
👤 Switches to another user (e.g., `su clouduser`).  
You’ll be prompted to enter that user’s password.

---

## 🧠 **Summary**
In this lesson, I practiced:
- Creating and managing users and groups 👥  
- Setting ownership and permissions for files 🔐  
- Securing sensitive files and directories 🧱  
- Testing and verifying permission setups 🔍  

---

## 💡 Next Steps
- Learn **file permission numbers (octal notation)**  
- Practice **recursive permissions (chmod -R)**  
- Explore **ACL (Access Control Lists)** for advanced setups  

---

### ✍️ Author
**Hashir Afridi**  
📘 *AWS Beginner — Lesson 5: Configuring User and Group Permissions in Linux*

---

### 🗂️ Repository Structure (Updated)
```
aws-learning-journey/
│
├── README.md
├── ec2-basics/
│   └── README.md
├── web-server-nginx/
│   └── README.md
├── linux-basics/
│   └── README.md
├── user-group-management/
│   └── README.md
├── permissions-management/
│   └── README.md   # ← This lesson
└── s3-bucket-setup/
    └── README.md
```
