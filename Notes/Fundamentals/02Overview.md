# ☁️ Google Cloud Platform (GCP)

> **GCP is Google's cloud platform that provides computing, storage, networking, databases, security and other services over the Internet.**

Instead of buying and maintaining physical infrastructure, users can create and manage cloud resources through GCP.

---

## 🌐 1. What does GCP provide?

GCP offers different services for building, deploying and managing applications.

| Category   | What it does                    | GCP example          |
| ---------- | ------------------------------- | -------------------- |
| Compute    | Runs applications               | Compute Engine       |
| Storage    | Stores files and objects        | Cloud Storage        |
| Networking | Connects and protects resources | VPC                  |
| Databases  | Stores application data         | Cloud SQL, Firestore |
| Containers | Runs containerized applications | GKE, Cloud Run       |
| Security   | Controls access                 | IAM                  |
| Monitoring | Observes application health     | Cloud Monitoring     |

💡 **Remember:** GCP is not just for hosting websites. It provides infrastructure and managed services for complete applications.

---

## 🏗️ 2. How do we use GCP?

You can interact with GCP in three common ways:

### 1. Google Cloud Console

A web-based interface where you can create, configure and monitor resources.

Example: Creating a VM through the browser.

### 2. Cloud Shell

A browser-based terminal provided by Google Cloud.

It comes with Google Cloud tools such as the `gcloud` CLI.

### 3. gcloud CLI

A command-line tool used to manage GCP resources.

Example:

```bash
gcloud compute instances list
```

This command lists Compute Engine VM instances in the selected project.

### Quick comparison

| Tool          | Meaning                                |
| ------------- | -------------------------------------- |
| Cloud Console | Manage GCP using a graphical interface |
| Cloud Shell   | Use a terminal in your browser         |
| gcloud CLI    | Manage GCP using commands              |

---

## 📁 3. What is a GCP Project?

A **Project** is an important unit used to organize and manage resources in GCP.

For example, you can create separate projects for different applications:

```text
Google Cloud Account
        │
        ├── Project: Food-Redistribution
        │       ├── VM
        │       ├── Storage Bucket
        │       └── Networking
        │
        └── Project: Employee-Management
                ├── Cloud Run
                └── Database
```

Projects help organize resources and manage access, billing and service usage.

⚠️ **Important:** A project is not the same as a VM. A VM is a resource created inside a project.

---

## 🧩 4. GCP Resource Hierarchy

GCP resources can be organized using a hierarchy.

```text
Organization
     │
   Folders
     │
   Projects
     │
   Resources
```

| Level        | Purpose                                  |
| ------------ | ---------------------------------------- |
| Organization | Represents an organization               |
| Folder       | Groups projects                          |
| Project      | Organizes resources and manages settings |
| Resource     | Actual service, such as a VM or bucket   |

**Example:**

A company may have one organization, separate folders for departments, and different projects for applications.

💡 Not every individual user has an Organization node. Personal accounts may work directly with projects.

---

## 🛠️ 5. Important GCP Services to Know

These are the services you’ll encounter while learning cloud and DevOps.

| Service           | Simple meaning                                           |
| ----------------- | -------------------------------------------------------- |
| Compute Engine    | Virtual machines                                         |
| Cloud Storage     | Object storage for files                                 |
| VPC               | Virtual network                                          |
| Cloud SQL         | Managed relational database                              |
| Firestore         | NoSQL document database                                  |
| Cloud Run         | Runs containerized applications without managing servers |
| GKE               | Managed Kubernetes                                       |
| IAM               | Manages who can access what                              |
| Cloud Monitoring  | Monitors resources and applications                      |
| Artifact Registry | Stores container images and other artifacts              |

---

## ⚔️ 6. GCP vs AWS vs Azure

All three are major cloud platforms. They provide many similar categories of services, but their names, features and implementations differ.

| Category             | Google Cloud   | AWS     | Microsoft Azure                 |
| -------------------- | -------------- | ------- | ------------------------------- |
| Virtual Machines     | Compute Engine | EC2     | Virtual Machines                |
| Object Storage       | Cloud Storage  | S3      | Blob Storage                    |
| Virtual Network      | VPC            | VPC     | Virtual Network                 |
| Managed SQL Database | Cloud SQL      | RDS     | Azure SQL Database              |
| Kubernetes           | GKE            | EKS     | AKS                             |
| Identity and Access  | Cloud IAM      | AWS IAM | Microsoft Entra ID / Azure RBAC |

### Easy way to understand

```text
             Cloud Platforms
                    │
       ┌────────────┼────────────┐
       ↓            ↓            ↓
      GCP          AWS         Azure
       │            │            │
   Compute       Compute      Compute
   Storage       Storage      Storage
   Networking    Networking   Networking
   Databases     Databases    Databases
```

💡 **Interview point:** The core cloud concepts are transferable. For example, learning VMs, storage, networking and IAM in GCP helps you understand similar services in AWS and Azure.

---

## 🎯 Interview Questions

### What is GCP?

> Google Cloud Platform is a cloud computing platform that provides services such as compute, storage, networking, databases and security over the Internet.

### What is a GCP project?

> A project is a unit used to organize cloud resources and manage settings such as access, billing and service usage.

### What is the difference between Cloud Console and Cloud Shell?

> Cloud Console is a graphical web interface, while Cloud Shell provides a browser-based command-line environment.

### What is the gcloud CLI?

> The gcloud CLI is a command-line tool used to manage Google Cloud resources.

### Are GCP, AWS and Azure the same?

> They are different cloud platforms that provide many similar categories of services, but their services, features and implementations can differ.

---

## 🧠 One-line Summary

> **GCP provides cloud services; projects organize resources; Console, Cloud Shell and gcloud CLI help us manage them.**
