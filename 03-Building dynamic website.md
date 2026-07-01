# ☁️ Lab 03: Building a Dynamic Web Application with Compute Engine, Cloud SQL & Cloud Storage

## 🎯 Project Overview

In this lab, I built a simple cloud-hosted blog application by integrating three core Google Cloud services.

Unlike the previous lab where Marketplace deployed everything automatically, this time I manually provisioned the infrastructure, configured a virtual machine, connected it to a managed Cloud SQL database, and integrated Cloud Storage for hosting application assets.

The final result was a web application capable of communicating with a database while serving static content directly from Cloud Storage.

---

# 🧠 Concept Breakdown (What I Actually Built)

## 1. Compute Engine

Compute Engine provides Virtual Machines running inside Google's global infrastructure.

In this lab, the VM acted as the web server hosting the PHP application.

Responsibilities:
- Run Apache Web Server
- Execute PHP code
- Process client requests
- Connect to Cloud SQL
- Display the final webpage

Think of it as the **brain of the application**.

---

## 2. Cloud SQL

Cloud SQL is Google's fully managed relational database service.

Instead of installing MySQL manually on the VM, Google manages:

- database installation
- updates
- storage
- backups
- availability

The application only connects to the database using its Public IP and credentials.

Think of Cloud SQL as the **secure storage room** where application data lives.

---

## 3. Cloud Storage

Cloud Storage provides highly durable object storage.

Instead of storing images inside the web server, the application loads them directly from a Cloud Storage bucket using a public URL.

Benefits:

- scalable
- highly available
- low maintenance
- globally accessible

Think of Cloud Storage as the **media library** for the application.

---

## 4. Startup Script

Instead of manually installing software after the VM starts, I used a **Startup Script**.

Whenever the VM boots, Google automatically executes this script.

```bash
#!/bin/bash
apt-get install apache2 php php-mysql -y
service apache2 restart
```

This automatically installs:

- Apache
- PHP
- MySQL PHP Driver

and starts the web server without manual configuration.

This demonstrates basic **Infrastructure Automation**.

---

# 🛠️ Click-by-Click Execution Steps

## Step 1 — Launch Google Cloud Console

(Add Screenshot)

- Opened the lab in an Incognito window.
- Logged in using temporary lab credentials.
- Opened Google Cloud Console.

---

## Step 2 — Create Compute Engine VM

(Add Screenshot)

Configured:

- Name: bloghost
- Machine Type: e2-standard-2
- Debian 12
- Allow HTTP Traffic
- Added Startup Script

Created the VM and noted:

- Internal IP
- External IP

---

## Step 3 — Create Cloud Storage Bucket

(Add Screenshot)

Using Cloud Shell:

- Created a globally unique bucket.
- Downloaded the sample banner image.
- Uploaded it into the bucket.
- Made the image publicly readable.

---

## Step 4 — Create Cloud SQL Instance

(Add Screenshot)

Created a MySQL Cloud SQL instance named:

blog-db

Configured:

- Sandbox edition
- Database password
- User account
- Authorized Network
- Public IP

Recorded the SQL Public IP.

---

## Step 5 — Build the PHP Application

(Add Screenshot)

Connected to the VM using SSH.

Created:

index.php

The PHP application:

- loads HTML
- connects to Cloud SQL
- displays database connection status

Initially the connection failed because the SQL IP and password were placeholders.

---

## Step 6 — Configure Database Connectivity

(Add Screenshot)

Updated:

- Cloud SQL Public IP
- Database Password

Restarted Apache.

Reloaded the webpage.

Verified:

Connected Successfully

This confirmed successful communication between Compute Engine and Cloud SQL.

---

## Step 7 — Integrate Cloud Storage

(Add Screenshot)

Retrieved the public URL of the image stored inside Cloud Storage.

Modified:

index.php

Added:

<img src="Cloud Storage Public URL">

Restarted Apache.

Reloaded the webpage.

The banner image was now served directly from Cloud Storage.

---

## 📸 Visual Evidence

### Step 1 — Console Login

(Image)

---

### Step 2 — VM Creation

(Image)

---

### Step 3 — Startup Script Configuration

(Image)

---

### Step 4 — Cloud Storage Bucket

(Image)

---

### Step 5 — Cloud SQL Deployment

(Image)

---

### Step 6 — Database Connection

(Image)

---

### Step 7 — Successful Web Application

(Image)

---

# 💡 Key Takeaways

## 1. Infrastructure Provisioning

I manually provisioned cloud infrastructure instead of relying on Marketplace automation.

---

## 2. Infrastructure Automation

Startup Scripts automatically installed and configured Apache and PHP whenever the VM booted.

---

## 3. Managed Databases

Cloud SQL removed the need to install and manage MySQL manually while still providing a standard relational database.

---

## 4. Object Storage

Cloud Storage hosted static files separately from the application server, improving scalability and maintainability.

---

## 5. Multi-Service Integration

This lab demonstrated how multiple Google Cloud services collaborate:

Client Browser
↓
Compute Engine VM
↓
Cloud SQL Database

↓

Cloud Storage (Images)

This is the basic architecture behind many modern cloud-hosted web applications.

---

# 🚀 Next Practical Steps

- Secure the application using HTTPS.
- Replace Public IP connectivity with Private IP.
- Store database passwords in Secret Manager.
- Deploy the application behind a Load Balancer.
- Automate deployment using Terraform or Deployment Manager.