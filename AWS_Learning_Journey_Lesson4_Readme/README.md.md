# 👨‍💻 AWS Learning Journey — Lesson 4: 👥 File, User & Group Management in Linux

Welcome to **Lesson 4** of my AWS Learning Journey!  
In this class, I learned about **file systems**, **user management**, and **group management** — essential skills for handling permissions and organizing users in a Linux environment. 💪

---

## 🧱 **Linux File System Overview**

| Directory | Description |
|------------|-------------|
| `/` | 🏠 The **root directory** — top-level directory of the entire Linux file system. |
| `/home` | 👤 Contains individual **user directories** (e.g., `/home/john`). |
| `/etc` | ⚙️ Stores **system configuration files** and settings. |
| `/var` | 📦 Contains **variable data** like logs, cache, and temporary files. |
| `/usr` | 🧰 Holds **user-installed programs** and libraries. |
| `/bin` | 🧮 Contains essential **binary executables** (commands like `ls`, `cat`, etc.). |
| `/sbin` | 🔧 Similar to `/bin` but for **system binaries** (for admin commands). |

---

## 🛣️ **Absolute vs Relative Paths**

| Type | Example | Description |
|------|----------|-------------|
| **Absolute Path** | `/root/home/home2/f.txt` | 📍 Full path starting from the root directory `/`. |
| **Relative Path** | `home2/f.txt` | 🚶 Path relative to the current working directory. |

🧩 **Tip:** Absolute paths always start with `/`, while relative paths don’t.

---

## 👥 **User Management**

| Command | Description |
|----------|-------------|
| `adduser <username>` | ➕ Creates a new user (must be run as root). |
| `sudo adduser <username>` | ⚡ Creates a new user with admin privileges (using sudo). |
| `cat /etc/passwd` | 📜 Displays a list of all system users. |
| `grep <username> /etc/passwd` | 🔍 Searches for details of a single user. |

🧩 **Example:**
```bash
sudo adduser john_dev
cat /etc/passwd
grep john_dev /etc/passwd
```

---

## 🧑‍🤝‍🧑 **Group Management**

| Command | Description |
|----------|-------------|
| `sudo groupadd devops_team` | 🏗️ Creates a new group named `devops_team`. |
| `cat /etc/group` | 📘 Displays all existing groups. |
| `grep devops_team /etc/group` | 🔍 Searches for a specific group. |
| `getent group devops_team` | 🧾 Shows detailed info about the group. |

🧩 **Example:**
```bash
sudo groupadd devops_team
cat /etc/group
grep devops_team /etc/group
getent group devops_team
```

---

## 🔒 **Adding Users to Groups**

| Command | Description |
|----------|-------------|
| `sudo usermod -aG <groupname> <username>` | 👥 Adds an existing user to a group. |
| `groups <username>` | 📋 Lists all groups the user belongs to. |
| `sudo usermod -aG sudo <username>` | ⚙️ Grants **admin privileges** to a user. |

🧩 **Example:**
```bash
sudo usermod -aG devops_team john_dev
groups john_dev
sudo usermod -aG sudo john_dev
```

---

## 🧠 **Quick Recap**

✅ Learned about Linux file system hierarchy  
✅ Understood absolute vs relative paths  
✅ Created and managed users and groups  
✅ Granted users admin privileges using `sudo`  

---

## 💡 Next Steps
- Learn about **file permissions** (`chmod`, `chown`)  
- Manage **ownership and access control**  
- Explore **user deletion and password policies**

---

### ✍️ Author
**Hashir Afridi**  
📘 *AWS Beginner — Lesson 4: User and Group Management*

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
│   └── README.md   # ← This lesson
└── s3-bucket-setup/
    └── README.md
```
