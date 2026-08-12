# ☁️ Project 2 – The Server Commander

## Cloud Computing Industrial Training – DecodeLabs

This project demonstrates the deployment and configuration of a Linux-based web server on **Amazon Web Services (AWS)** using **Amazon EC2**.

The objective was to provision a cloud virtual machine, securely access it through SSH, install and configure the Apache HTTP Server, and deploy a custom **“Welcome to DecodeLabs”** webpage.

---

## 🎯 Project Objective

The main objectives of this project were to:

* Launch a Linux virtual machine on AWS EC2
* Configure secure SSH access
* Install Apache using the Linux command line
* Start and enable the Apache service
* Deploy a custom static webpage
* Access and verify the website through the EC2 public IP address

---

## 🛠️ Technologies Used

* Amazon Web Services (AWS)
* Amazon EC2
* Amazon Linux 2023
* Apache HTTP Server
* Linux Command Line
* SSH
* HTML & CSS
* AWS Security Groups

---

## 🏗️ Architecture

```text
User / Browser
      |
      | HTTP - Port 80
      v
AWS Security Group
      |
      v
Amazon EC2 Instance
      |
      |-- Amazon Linux 2023
      |-- Apache HTTP Server
      |
      v
Welcome to DecodeLabs
```

SSH access is restricted through the EC2 Security Group for server administration.

---

## 🚀 Implementation

### 1. Launch EC2 Instance

An Amazon EC2 instance was created using:

* **Operating System:** Amazon Linux 2023
* **Instance Type:** Micro instance
* **Public IPv4:** Enabled
* **Key Pair:** Configured for secure SSH authentication

The Security Group was configured to permit the required traffic.

---

### 2. Connect to the Server Using SSH

The EC2 instance was accessed securely using an SSH key pair.

Example:

```bash
ssh -i "server-commander-key.pem" ec2-user@<EC2-PUBLIC-IP>
```

This provided command-line access to the Amazon Linux server.

---

### 3. Update the Linux Server

The operating system packages were updated:

```bash
sudo dnf update -y
```

---

### 4. Install Apache Web Server

Apache HTTP Server was installed using:

```bash
sudo dnf install httpd -y
```

The Apache service was then started:

```bash
sudo systemctl start httpd
```

Apache was enabled to automatically start after system reboot:

```bash
sudo systemctl enable httpd
```

---

### 5. Verify Apache Status

The Apache service was verified using:

```bash
sudo systemctl status httpd
```

The result confirmed:

```text
Active: active (running)
```

This verified that the web server was successfully running.

---

## 🌐 Custom Webpage Deployment

A custom webpage was created inside Apache's default document root:

```bash
sudo nano /var/www/html/index.html
```

The webpage includes:

* Welcome to DecodeLabs
* Project 2 – The Server Commander
* AWS EC2 deployment information
* Apache server deployment status
* Custom HTML/CSS styling

The website was then accessed through the EC2 public IPv4 address:

```text
http://<EC2-PUBLIC-IP>
```

---

## 🔐 Security Configuration

AWS Security Groups were used as the instance-level firewall.

The configuration included:

| Service | Protocol | Port | Purpose                             |
| ------- | -------- | ---: | ----------------------------------- |
| SSH     | TCP      |   22 | Secure remote server administration |
| HTTP    | TCP      |   80 | Public web access                   |

SSH access should be restricted to a trusted IP address rather than opened to the entire internet.

---

## 📸 Project Evidence

The following screenshots can be included in the repository:

1. EC2 instance successfully running
2. EC2 Security Group configuration
3. Successful SSH connection
4. Apache installation
5. Apache `active (running)` status
6. Custom **Welcome to DecodeLabs** webpage in the browser

Recommended repository structure:

```text
project-2-server-commander/
│
├── README.md
│
└── screenshots/
    ├── 01-ec2-instance.png
    ├── 02-security-group.png
    ├── 03-ssh-connection.png
    ├── 04-apache-installation.png
    ├── 05-apache-running.png
    └── 06-decodeLabs-webpage.png
```

---

## ✅ Project Result

Project 2 was successfully completed.

The final solution demonstrates the ability to:

* Provision cloud compute resources
* Work with a Linux cloud server
* Configure SSH access
* Install software through the command line
* Manage Linux services with `systemctl`
* Configure basic network access using Security Groups
* Deploy and host a static website on AWS EC2

The final **“Welcome to DecodeLabs”** webpage was successfully hosted using Apache on an Amazon EC2 instance.

---

## 📚 Key Skills Gained

* AWS EC2
* Linux Server Administration
* SSH
* Apache Web Server
* Security Groups
* Cloud Networking
* HTML/CSS Deployment
* Web Server Troubleshooting

---

## 📌 Project Information

**Project:** Project 2 – The Server Commander
**Program:** Cloud Computing Industrial Training
**Platform:** AWS
**Training Provider:** DecodeLabs
**Batch:** 2026
**Status:** ✅ Completed
