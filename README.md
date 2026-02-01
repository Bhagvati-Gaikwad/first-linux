Connect AWS EC2 to Local System (Terminal Commands)

This project demonstrates **step-by-step terminal commands** to connect an **AWS EC2 Linux instance** to a **local system** using SSH.

---

## 🧰 Prerequisites

* AWS account
* EC2 Linux instance (Amazon Linux / Ubuntu)
* `.pem` key file downloaded from AWS
* Terminal access:

  * Linux / macOS Terminal
  * Windows: Git Bash or WSL

---

## 📂 Step 1: Locate Your Key Pair File

After downloading your EC2 key pair, move to the directory where it exists.

```bash
cd ~/Downloads
```

List files to confirm:

```bash
ls
```

Example output:

```
my-ec2-key.pem
```

---

## 🔐 Step 2: Change Key File Permissions (Mandatory)

SSH requires strict permissions for private keys.

```bash
chmod 400 my-ec2-key.pem
```

Verify permissions:

```bash
ls -l my-ec2-key.pem
```

Expected output:

```
-r--------  1 user user  my-ec2-key.pem
```

---

## 🌐 Step 3: Get EC2 Public IP Address

From AWS EC2 Dashboard:

* Select your instance
* Copy **Public IPv4 address**

Example:

```
13.233.xxx.xxx
```

---

## 🔑 Step 4: Connect to EC2 Using SSH

### For Amazon Linux:

```bash
ssh -i my-ec2-key.pem ec2-user@13.233.xxx.xxx
```

### For Ubuntu:

```bash
ssh -i my-ec2-key.pem ubuntu@13.233.xxx.xxx
```

When prompted:

```text
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text
yes
```

✅ You are now connected to the EC2 instance.

---

## 🖥️ Step 5: Verify Connection on EC2

Run basic Linux commands:

```bash
whoami
```

Output:

```
ec2-user
```

```bash
pwd
```

```bash
uname -a
```

```bash
ls
```

---

## 📦 Step 6: Update System Packages

### Amazon Linux:

```bash
sudo yum update -y
```

### Ubuntu:

```bash
sudo apt update && sudo apt upgrade -y
```

---

## 🛠️ Step 7: Install Basic Tools

```bash
sudo yum install git -y
```

or (Ubuntu):

```bash
sudo apt install git -y
```

Check installation:

```bash
git --version
```

---

## 📊 Step 8: Monitor System Resources

```bash
top
```

```bash
df -h
```

```bash
free -m
```

---

## 🗂️ Step 9: Create & Manage Files

Create a directory:

```bash
mkdir linux-practice
```

Navigate:

```bash
cd linux-practice
```

Create a file:

```bash
touch demo.txt
```

Edit file:

```bash
nano demo.txt
```

View file:

```bash
cat demo.txt
```

---

## 🔐 Step 10: Exit EC2 Instance

```bash
exit
```

You are now back on your **local system terminal**.

---

## ❌ Common Errors & Fixes

### Permission denied (publickey)

✔ Fix:

```bash
chmod 400 my-ec2-key.pem
```

✔ Ensure correct username (`ec2-user` or `ubuntu`)

---

### Connection timeout

✔ Check:

* EC2 instance is running
* Security Group allows **port 22**
* Correct public IP

---

## 🧠 Key Concepts Learned

* SSH authentication
* Linux file permissions
* AWS EC2 access
* Terminal-based cloud management
* DevOps foundational workflow

---

## 🎯 Why This Matters for DevOps

Every DevOps Engineer must:

* Access cloud servers via SSH
* Manage Linux systems remotely
* Secure access using key pairs

This project proves **real-world cloud & Linux skills**.

---

## ⭐ Conclusion

Connecting to an EC2 instance via terminal is one of the **first real DevOps skills**.
This repository provides a **clear, command-level walkthrough** to master it.

<img width="2880" height="1635" alt="image" src="https://github.com/user-attachments/assets/02221fe9-c2d3-45d0-8b8b-23c2cad02d06" />
<img width="2880" height="1704" alt="image" src="https://github.com/user-attachments/assets/50b9eeeb-f02a-4691-a551-5c5eadbec54c" />
