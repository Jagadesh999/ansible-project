# ansible-project
### **Ansible Playbooks for Server Automation**  

This repository contains multiple Ansible playbooks to automate common server configurations and deployments.  

## **Playbooks Included**  

### 🚀 **1. Docker Installation**  
Installs and configures Docker on the target servers.  
- Pulls Docker from the official repository  
- Starts and enables the Docker service  
- Compatible with **Debian-based** systems  

**File:** `docker-install.yml`  

### 🔄 **2. Linux Patching & Updates**  
Automates system updates to keep the servers secure and up-to-date.  
- Updates all installed packages  
- Supports both **Debian-based** and **RHEL-based** systems  
- Reboots the system if required  

**File:** `linux-patching.yml`  

### 🌐 **3. HTTPD Installation & Web Page Setup**  
Deploys an **Apache (HTTPD)** web server with a custom welcome page.  
- Installs Apache (`apache2` for Debian, `httpd` for RHEL)  
- Starts and enables the web service  
- Creates an **index.html** file with the following message:  

  > **"Hey friends, life is full of surprises! Cherish your loved ones, respect everyone, and keep hoping for better things ahead."**  

**File:** `httpd-setup.yml`  

---

## **How to Use These Playbooks**  

### **Step 1: Clone the Repository**  
```bash
git clone https://github.com/jagadesh999/ansible-project.git
cd ansible-project
```

### **Step 2: Define Your Inventory**  
Create an `inventory.ini` file to define the target servers:  
```ini
[web]
172.31.92.147

[db]
172.31.80.123

[all:vars]
ansible_user=ubuntu
ansible_ssh_private_key_file=~/.ssh/id_rsa
```

### **Step 3: Run the Playbooks**  

Run the **Docker installation** playbook:  
```bash
ansible-playbook -i inventory.ini docker-install.yml
```

Run the **Linux patching** playbook:  
```bash
ansible-playbook -i inventory.ini linux-patching.yml
```

Run the **HTTPD installation** playbook:  
```bash
ansible-playbook -i inventory.ini httpd-setup.yml
``
```

---
