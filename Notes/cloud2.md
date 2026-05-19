# 🏢 Google Cloud Resource Management & Security

## 📊 Google Cloud Resource Hierarchy

Google Cloud organizes resources in a hierarchical structure with 4 levels:

```
Level 4: Organization Node (Top)
├── Level 3: Folders
│   ├── Level 2: Projects
│   │   └── Level 1: Resources (VMs, Cloud Storage Buckets, BigQuery Tables, etc.)
```

### 🎯 Understanding Each Level

#### **Level 1: Resources**
- **Definition:** Individual Google Cloud services and components
- **Examples:** 
  - Compute Engine VMs
  - Cloud Storage buckets
  - BigQuery tables
  - Cloud Databases
- **Key Point:** Each resource belongs to exactly ONE project

#### **Level 2: Projects**
Projects are the basis for enabling and using GCP services. Each project acts as a container for resources with separate management and billing.

| Property | Description |
|----------|-------------|
| **Separate Entity** | Each project exists independently under organization node |
| **Resource Container** | Holds resources; each resource belongs to only ONE project |
| **User Management** | Projects can have different owners and users |
| **Billing** | Projects are billed and managed separately |
| **API Management** | Projects enable/disable APIs and manage services |

#### **Project Identifiers** 🆔

Each GCP project has THREE unique identifiers:

| Identifier | Characteristics | Assigned By | Mutability |
|-----------|-----------------|------------|-----------|
| **Project ID** | Globally unique identifier | Google Cloud (but chosen by user during creation) | Mutable only during creation |
| **Project Name** | Human-readable identifier | User chooses | Mutable (can repeat across projects) |
| **Project Number** | Globally unique numeric ID | Google Cloud | Immutable (never changes) |

**Example:**
```
Project ID: my-awesome-app-12345
Project Name: "Production App" (could be non-unique)
Project Number: 987654321000 (unique & permanent)
```

#### **Level 3: Folders**
- **Purpose:** Organize projects and apply policies hierarchically
- **Policy Inheritance:** Resources in a folder inherit policies and permissions assigned to the folder
- **Use Cases:**
  - **Centralized Policies:** Multiple teams working on different projects can inherit common security policies from a shared parent folder
  - **Team Organization:** Different teams get individual folders for their own policies
  - **Requirement:** Organization node MUST exist to use folders

#### **Level 4: Organization Node**
- **Definition:** Top-level container for folders, projects, and all resources
- **Role:** Manages organization-wide policies and permissions

---

## 🔧 Resource Manager Tool

### What is it?
The Resource Manager is a Google-provided API tool that manages and tracks your cloud resources.

### Key Capabilities

| Capability | Description |
|-----------|-------------|
| **List Resources** | Gather all projects associated with your account |
| **Create Projects** | Create new GCP projects programmatically |
| **Update Projects** | Modify project configurations |
| **Delete Projects** | Remove projects from your account |
| **Recover Projects** | Restore deleted projects within a recovery window |

### Access Methods
- **REST API** - Use standard HTTP requests
- **RPC API** - Use Remote Procedure Calls for more advanced operations

---

## 🔐 IAM (Identity and Access Management)

### What is IAM?

**Definition:** A framework that allows administrators to control who can do what on which resources.

```
IAM Policy = WHO + CAN DO WHAT + ON WHICH RESOURCE
```

### 👤 WHO - Principals (Users/Entities)

**Principals** are entities that can be granted permissions:

| Principal Type | Description | Example |
|---------------|-------------|---------|
| **Google Account** | Individual Google account | user@gmail.com |
| **Google Group** | Group of Google accounts | developers@company.com |
| **Service Account** | Account for applications/VMs | vm-instance@project.iam.gserviceaccount.com |
| **Cloud Identity Domain** | Organization's identity system | user@company.com (via Cloud Identity) |

**Note:** Each principal is identified by an email address as its unique identifier.

### 🎭 WHAT - IAM Roles

**Role:** A collection of permissions that define what actions a principal can perform.

#### Types of IAM Roles 🎯

##### **1. Basic Roles** (Legacy - Use with caution!)
When applied to a project, affects ALL resources in that project.

| Role | Permissions |
|------|------------|
| **Owner** | Full control; can manage everything including billing and access control |
| **Editor** | Can create, modify, and delete resources |
| **Viewer** | Read-only access to resources |
| **Billing Admin** | Manage billing and payment methods |

⚠️ **Warning:** Basic roles are too broad and affect entire projects. Prefer predefined/custom roles for better security!

##### **2. Predefined Roles** (Recommended ✅)
Google Cloud services offer specific predefined roles with fine-grained permissions.

- **Specificity:** Designed for specific services (e.g., Compute, Storage, Databases)
- **Scope:** Clearly define where the role can be applied
- **Example:** `roles/compute.instanceAdmin` - Manage Compute Engine instances only
- **Benefit:** Follow principle of least privilege

##### **3. Custom Roles** (Maximum Control)
Create your own roles with a specific set of permissions.

- **Flexibility:** Define exactly which permissions are needed
- **Use Case:** When predefined roles don't match your requirements
- **Benefit:** Fine-grained control for specialized teams

### 🔀 Permission Inheritance

When a principal is granted a role at a specific level in the resource hierarchy, the policy applies to:
- ✅ The chosen element
- ✅ ALL elements below it in the hierarchy

**Example:**
```
If "Editor" role granted at Project level:
├── Applies to entire project
├── Applies to all folders in project
└── Applies to all resources in those folders
```

### ⚠️ IAM Policy Evaluation Order

**CRITICAL:** IAM always follows this order when evaluating permissions:

1. 🚫 **Check DENY Policies FIRST** - If explicitly denied, access is blocked immediately
2. ✅ **Check ALLOW Policies** - If allowed (and not denied), access is granted

**Golden Rule:** A single DENY policy overrides all ALLOW policies!

---

## 🤖 Service Accounts

### What are Service Accounts?

**Definition:** Special accounts that allow applications and VMs to authenticate and interact with other Google Cloud services without human intervention.

### Key Characteristics

| Characteristic | Description |
|---------------|-------------|
| **Identification** | Named with an email address (like users) |
| **Authentication** | Use cryptographic keys instead of passwords |
| **Purpose** | Enable VM-to-service communication securely |
| **Example** | `my-app@my-project.iam.gserviceaccount.com` |

### Use Cases 💡

| Scenario | Benefit |
|----------|---------|
| **VM accessing Cloud Storage** | Service account grants only storage permissions; no credentials stored |
| **Application calling APIs** | App authenticates via key without embedding credentials in code |
| **Microservices communication** | Each service has minimal required permissions (least privilege) |
| **Batch jobs** | Automated jobs run with specific, limited permissions |

---

## ☁️ Cloud Identity

### What is Cloud Identity?

**Definition:** A centralized identity and access management solution for organizations to define policies, manage users, and manage groups.

### Key Features

| Feature | Description | Benefit |
|---------|-------------|---------|
| **User Management** | Centrally manage organization users | Enforce naming conventions, password policies |
| **Group Management** | Create and manage user groups | Easier permission assignment to teams |
| **Policy Definition** | Set organization-wide policies | Consistent security across all employees |
| **Google Admin Console** | Web interface for management | Easy to use without technical skills |
| **Integration** | Works with Google Cloud and other services | Single source of truth for identity |

### Why Use Cloud Identity?

✅ **Centralized Control** - Manage all users from one place  
✅ **Scalability** - Works for organizations of any size  
✅ **Security** - Enforce password policies, 2FA, etc.  
✅ **Compliance** - Track user activities and access  
✅ **Integration** - Works with Cloud IAM seamlessly  

---

## 🎓 Key Takeaways

| Concept | Key Point |
|---------|-----------|
| **Hierarchy** | Organization → Folders → Projects → Resources |
| **Projects** | Separate billing, management, and API enablement units |
| **IAM** | Control access through WHO (principals) → WHAT (roles) → WHERE (resources) |
| **Deny First** | DENY policies are evaluated before ALLOW policies |
| **Service Accounts** | Enable secure VM-to-service communication without credentials |
| **Cloud Identity** | Centralized user and group management |
| **Principle of Least Privilege** | Grant minimum necessary permissions using predefined/custom roles |

---
