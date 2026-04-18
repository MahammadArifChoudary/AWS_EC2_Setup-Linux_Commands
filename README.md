# AWS_EC2_Setup-Linux_Commands
The complete steps to setup EC2-Instance on AWS and Linux Commands

# 🚀 AWS EC2 Instance Setup Guide

This guide provides step-by-step instructions to launch and configure an EC2 instance on AWS.
## 📌 Prerequisites

Before starting, ensure you have:

- An active AWS account  
- Basic knowledge of Linux commands  
- SSH client (Terminal / Git Bash / PowerShell)

## 🏗️ Step 1: Sign in to AWS

1. Go to https://aws.amazon.com  
2. Click **Sign In to Console**  
3. Enter your credentials  

## 🖥️ Step 2: Open EC2 Dashboard

1. Search for **EC2** in the AWS search bar  
2. Click on EC2 service  
3. Open the EC2 Dashboard  

## ⚙️ Step 3: Launch an Instance

1. Click **Launch Instance**  
2. Enter a name for your instance  

Example: My EC2-Server

## 💿 Step 4: Choose AMI (Operating System)

Select an OS image:

- Ubuntu Server 22.04 LTS (Recommended)
- Amazon Linux
- Windows Server

## 💡 Step 5: Choose Instance Type

Select: t2.micro
- Free Tier eligible  
- Suitable for beginners and small projects  

## 🔑 Step 6: Create Key Pair

1. Click **Create new key pair**  
2. Configure:
   - Name: `my-key`
   - Type: RSA  
   - Format: `.pem`  
3. Click **Create Key Pair**  
4. Download and store it securely  

⚠️ Important: This file is required to connect to your instance.

## 🌐 Step 7: Configure Network Settings

Allow the following:

| Type   | Port | Description       |
|--------|------|------------------|
| SSH    | 22   | Remote access    |
| HTTP   | 80   | Web traffic      |
| HTTPS  | 443  | Secure traffic   |

For testing: Allow SSH from: 0.0.0.0/0

⚠️ Not recommended for production use.

## 💾 Step 8: Configure Storage

- Default: 8 GB  
- Increase if needed  

## 🚀 Step 9: Launch Instance

1. Click **Launch Instance**  
2. Wait until status shows: running

## 🔌 Step 10: Connect to Instance

### Get Public IP
- Go to EC2 Dashboard → Instances  
- Copy Public IPv4 Address  

### Connect via SSH

#### Linux / Mac
```bash
chmod 400 my-key.pem
ssh -i my-key.pem ubuntu@<PUBLIC_IP>

Windows (PowerShell / Git Bash)
ssh -i my-key.pem ubuntu@<PUBLIC_IP>
Replace <PUBLIC_IP> with your instance IP.

🔄Step 11: Update System
sudo apt update
sudo apt upgrade -y

🧰 Step 12: Install Basic Tools
sudo apt install -y docker.io python3-pip


                                                      **Linux Commands**

# 🐧 Linux Commands Cheat Sheet

---

## 📌 1. System Commands / Information

| No | Command | Description |
|----|--------|-------------|
| 01 | uname | Get OS type |
| 02 | uname -s | Kernel name |
| 03 | uname -r | Kernel release |
| 04 | uname -v | Kernel version |
| 05 | uname -m | Machine hardware type |
| 06 | uname -p | Processor type |
| 07 | uname -a | All OS information |
| 08 | uptime | System running time |
| 09 | uptime -p | Pretty uptime |
| 10 | hostname | System hostname |
| 11 | hostname -i | Private IP |
| 12 | hostname <name> | Change hostname |
| 13 | hostnamectl set-hostname <name> | Set hostname |
| 14 | date | Current date |
| 15 | timedatectl | Timezone info |
| 16 | timedatectl set-timezone Asia/Kolkata | Set timezone |
| 17 | who | Logged-in users |
| 18 | whoami | Current user |

### ⏱️ Extra Date Commands

| No | Command | Description |
|----|--------|-------------|
| 19 | date +"%d" | Day |
| 20 | date +"%m" | Month |
| 21 | date +"%y" | Year |
| 22 | date +"%H" | Hour |
| 23 | date +"%M" | Minutes |
| 24 | date +"%S" | Seconds |
| 25 | date +"%D" | MM/DD/YY |
| 26 | date +"%F" | YYYY-MM-DD |
| 27 | date +"%A" | Day name |
| 28 | date +"%B" | Month name |
| 29 | date +"%C" | Century |

---

## 💻 2. Hardware Commands

| No | Command | Description |
|----|--------|-------------|
| 30 | df | Disk usage |
| 31 | df -h | Human readable disk |
| 32 | df -t | Filesystem type |
| 33 | du | Disk usage (files/folders) |
| 34 | du -h | Human readable |
| 35 | du -s | Total folder size |
| 36 | free | Memory usage |
| 37 | free -h | Human readable memory |
| 38 | free -t | Total memory |
| 39 | lscpu | CPU info |
| 40 | lsblk | Block devices |
| 41 | lspci | PCI devices |
| 42 | lsusb | USB devices |

---

## ⚙️ 3. Process Management

| No | Command | Description |
|----|--------|-------------|
| 43 | ps | Current processes |
| 44 | ps aux | All processes |
| 45 | ps -f | Full format |
| 46 | ps -e / ps -A | All processes |
| 47 | top | Real-time processes |
| 48 | htop | Interactive viewer |
| 49 | kill <PID> | Kill process |
| 50 | kill -9 <PID> | Force kill |
| 51 | killall | Kill all processes |
| 52 | bg | Background job |
| 53 | fg | Foreground job |

---

## 📂 4. File Management

| No | Command | Description |
|----|--------|-------------|
| 54 | touch file | Create file |
| 55 | vim file | Edit file |
| 56 | nano file | Edit file |
| 57 | cat file | Show content |
| 58 | cat > file | Overwrite file |
| 59 | cat >> file | Append file |
| 60 | tac file | Reverse content |
| 61 | head file | First 10 lines |
| 62 | tail file | Last 10 lines |
| 63 | sed -n '5,9p' file | Lines 5–9 |
| 64 | mkdir dir | Create folder |
| 65 | ls | List files |
| 66 | ll | Detailed list |
| 67 | ls -l | Permissions view |
| 68 | ls -a | Hidden files |
| 69 | ls -t | Sort by time |
| 70 | ls -ltr | Oldest first |
| 71 | cd dir | Change dir |
| 72 | cd | Root/home |
| 73 | cd .. | Back |
| 74 | cd ../.. | Back twice |

---

## 🗑️ File Delete & Copy

| No | Command | Description |
|----|--------|-------------|
| 75 | rm file | Delete file |
| 76 | rm -f file | Force delete |
| 77 | rmdir dir | Delete empty dir |
| 78 | rm -r dir | Delete folder |
| 79 | cp src dest | Copy |
| 80 | mv src dest | Move/Rename |

---

## 👤 5. User Management

| No | Command | Description |
|----|--------|-------------|
| 81 | adduser user | Create user |
| 82 | usermod -l new old | Rename user |
| 83 | passwd user | Set password |
| 84 | cat /etc/passwd | List users |
| 85 | id user | User info |
| 86 | sudo -i | Root |
| 87 | su user | Switch user |
| 88 | userdel user | Delete user |
| 89 | ps -u user | User process |
| 90 | visudo | Sudo access |
| 91 | useradd -e date user | Expiry |
| 92 | ls -ld username | Permissions |

---

## 👥 6. Group Management

| No | Command | Description |
|----|--------|-------------|
| 93 | groupadd group | Create group |
| 94 | cat /etc/group | List groups |
| 95 | groupdel group | Delete group |
| 96 | grep group /etc/group | Find group |
| 97 | usermod -aG group user | Add user |
| 98 | gpasswd -d user group | Remove user |
| 99 | groupmod -n new old | Rename group |

---

## 🔐 7. Ownership

| No | Command | Description |
|----|--------|-------------|
| 100 | chown user file | Change owner |
| 101 | chgrp group file | Change group |
| 102 | chown user:group file | Both |
| 103 | chown -R user:group dir | Recursive |

---

## 🔑 8. Permissions

| No | Command | Description |
|----|--------|-------------|
| 104 | chmod u+rwx file | Add permission |
| 105 | chmod ugo-rwx file | Remove permission |
| 106 | chmod 644 file | Numeric permission |

---

## 🌐 9. Network Commands

| No | Command | Description |
|----|--------|-------------|
| 107 | ping host | Check network |
| 108 | ifconfig | Network info |
| 109 | ip addr | IP address |
| 110 | netstat -tuln | Open ports |
| 111 | traceroute host | Route path |
| 112 | curl URL | API call |
| 113 | wget URL | Download |

---

## 📦 10. Package Management

### Ubuntu/Debian

| Command | Description |
|--------|-------------|
| apt update | Update packages |
| apt install pkg | Install |
| apt remove pkg | Remove |
| apt upgrade | Upgrade |

### RHEL/CentOS

| Command | Description |
|--------|-------------|
| yum install pkg | Install |
| yum remove pkg | Remove |

### DNF / Pacman / Snap / Flatpak also included similarly

---

## 📦 11. Compression

| No | Command | Description |
|----|--------|-------------|
| 123 | tar -cvf file.tar dir | Archive |
| 124 | tar -xvf file.tar | Extract |
| 125 | gzip file | Compress |
| 126 | gzip -d file | Decompress |
| 127 | zip file.zip files | Zip |
| 128 | unzip file.zip | Unzip |

---

## 🔍 12. Search Commands

| No | Command | Description |
|----|--------|-------------|
| 129 | find . -name file | Find file |
| 130 | find . -type d | Find folder |
| 131 | find . -perm 777 | Permission |
| 132 | find . -empty | Empty files |
| 140 | grep "word" file | Search word |
| 141 | grep -n word file | With line |
| 142 | grep -i word file | Ignore case |
| 143 | grep -l word file | File names |
| 144 | grep -c word file | Count |
