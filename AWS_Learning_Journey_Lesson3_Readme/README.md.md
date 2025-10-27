# 🧑‍💻 AWS Learning Journey — Lesson 3: 💻 Basic Linux Commands for EC2

Welcome to **Lesson 3** of my AWS Learning Journey!  
In this session, I’m learning essential **Linux commands** to manage my EC2 instance efficiently.  
These are the basic building blocks for navigating, editing, and controlling any Linux system. 🚀

---

## 🎯 Objective
Understand and practice basic Linux commands used for:
- 📂 Navigation  
- 📝 File Management  
- ⚙️ System Monitoring  
- 🔐 Permissions and Control

---

## 🧭 **Navigation Commands**

| Command | Description |
|----------|-------------|
| `pwd` | 📍 Prints the **current working directory** you are in. |
| `ls` | 📄 Lists files and folders in the current directory. |
| `ls -l` | 📋 Shows detailed file information like permissions, size, and owner. |
| `ls -al` | 🕵️ Lists **all** files including hidden ones with detailed info. |
| `cd <directory>` | 🚪 Changes directory to the specified folder. |
| `cd ~` | 🏠 Moves directly to the **home directory**. |

---

## 🧑‍💻 **User & Access Commands**

| Command | Description |
|----------|-------------|
| `whoami` | 🙋 Shows the current logged-in user. |
| `sudo -` | ⚡ Switches to the **superuser (root)** temporarily. |
| `exit` | 🚪 Exits from the current session or terminal. |

---

## 📝 **File Editing Commands**

### **Using Vim (Vi Editor)**
| Command | Description |
|----------|-------------|
| `vim file.txt` | 📘 Opens or creates a file in **Vim editor**. |
| `i` | ✍️ Enters insert mode to start typing text. |
| `Esc → :wq` | 💾 Saves and quits the Vim editor. |

### **Using Vi (Same as Vim)**
| Command | Description |
|----------|-------------|
| `vi file.txt` | 🗒️ Opens a file using Vi editor (similar to Vim). |
| `i` | ✍️ Enters insert mode to edit text. |
| `Esc → :wq` | 💾 Saves and exits Vi editor. |

### **Using Nano**
| Command | Description |
|----------|-------------|
| `nano file.txt` | 🧩 Opens file in Nano editor (easier for beginners). |
| `Ctrl + X`, then `Y` | 💾 Saves and exits the Nano editor. |

---

## 📁 **File and Directory Management**

| Command | Description |
|----------|-------------|
| `mkdir foldername` | 📂 Creates a new directory. |
| `touch filename` | 📄 Creates a new empty file. |
| `rm filename` | 🗑️ Deletes a specific file. |
| `rm -r foldername` | 🧹 Removes a directory and its contents recursively. |
| `cp filename filename2` | 📑 Copies a file to a new name or location. |
| `cp filename foldername` | 📦 Copies a file into a directory. |
| `mv filename /tmp` | 🚚 Moves a file to a new location (e.g., `/tmp`). |
| `ls /tmp/filename` | 🔍 Checks if the file exists in the target directory. |

🧩 **Difference:**  
- `cp` ➜ Copies the file (keeps original)  
- `mv` ➜ Moves the file (removes from original location)

---

## 📜 **Viewing Files & Logs**

| Command | Description |
|----------|-------------|
| `cat filename` | 📖 Displays file contents in the terminal. |
| `cat /var/log/syslog` | 🪵 Shows full system log output. |
| `less /var/log/syslog` | 🔍 Opens log file one screen at a time (use `q` to quit). |
| `head -n 10 /var/log/syslog` | 🧠 Shows the first 10 lines of a file. |
| `tail -n 10 /var/log/syslog` | 👣 Shows the last 10 lines of a file. |
| `journalctl -f` | 🛰️ Follows system logs live (real-time monitoring). |

🧩 **Difference:**  
- `cat` ➜ Shows full content instantly.  
- `less` ➜ Scrollable view (useful for long files).  
- `head` / `tail` ➜ Show beginning or end of files.  
- `journalctl -f` ➜ Live stream of logs.

---

## 🧠 **History & System Control**

| Command | Description |
|----------|-------------|
| `history` | 📜 Lists all previously executed commands. |
| `reboot` | 🔄 Restarts the system (normal user). |
| `sudo reboot` | ⚡ Restarts the system as root. |
| `sudo shutdown now` | 📴 Immediately shuts down the system. |

---

## 🧩 Summary
In this lesson, I learned to:
✅ Navigate the Linux file system  
✅ Manage files and directories  
✅ View and edit text files using different editors  
✅ Check logs and control system state  

---

## 💡 Next Steps
- Learn about **File Permissions** (`chmod`, `chown`)  
- Explore **System Monitoring Tools** (`top`, `htop`, `df`, `du`)  
- Practice **Shell scripting basics**

---

### ✍️ Author
**Hashir Afridi**  
📘 *AWS Beginner — Lesson 3: Mastering Linux Basics for EC2*

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
│   └── README.md   # ← This lesson
└── s3-bucket-setup/
    └── README.md
```
