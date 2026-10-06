
# GCP Resource Hierarchy

GCP organizes resources in a hierarchy:

```text
Organization
     ↓
  Folders
     ↓
  Projects
     ↓
  Resources
```

## 1. Organization

* Top-level container for a company/organization.
* Usually associated with **Google Workspace / Cloud Identity**.
* Personal Google accounts may not have an 
* Organization.

## 2. Folders

* **Optional**.
* Used to group projects.
* Useful for departments, teams, or environments.

```text
Organization
├── Development
│   ├── Project A
│   └── Project B
└── Production
    └── Project C
```

## 3. Project ⭐

The **main working boundary in GCP**.

Resources are created inside projects.

Example:

```text
Project
├── VM
├── VPC
├── Cloud Storage
└── Cloud Run
```

A project also provides a boundary for things like **APIs, IAM, quotas and billing association**.

### Project identifiers

| Identifier     | Meaning                       |
| -------------- | ----------------------------- |
| Project Name   | Human-readable name           |
| Project ID     | Unique string                 |
| Project Number | Unique number assigned by GCP |

## 4. Resources

The actual GCP services/infrastructure inside a project.

Examples:

* Compute Engine → VM
* Cloud Storage → Bucket
* Cloud SQL → Database
* Cloud Run → Service

---

## Easy Example

Think of a company:

```text
Organization = Company
Folder       = Department
Project      = Work environment
Resource     = Actual cloud service
```

For your personal GCP account, you'll mainly work with:

```text
Project
   ↓
Resources
```

You don't need an Organization or Folder to learn GCP.

---

## Why the Hierarchy Matters

The hierarchy helps GCP manage:

* **Access / IAM**
* **Policies**
* **Resources**
* **Projects**

Policies can generally be inherited from a parent level to child levels.

```text
Organization
     ↓
  Folder
     ↓
  Project
     ↓
 Resource
```

> Detailed IAM → `IAM/01-IAM.md`
> Billing → `04-Billing-and-Cost.md`

---

## Interview Point

**What is GCP Resource Hierarchy?**

> A structure used to organize and manage GCP resources: **Organization → Folders → Projects → Resources**.

### Remember

**Organization → Folder → Project → Resource**
