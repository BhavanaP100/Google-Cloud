# 🌐 Virtual Private Cloud (VPC)

## What is Virtual Private Cloud (VPC)?

**VPC:** A secure, individual, private cloud model hosted within a public cloud provider.

On VPC, customers can run code, host websites, store data, and anything else that can be done on a private cloud. A virtual private cloud is hosted remotely by a public cloud provider. This means VPC combines the scalability and convenience of public cloud computing.

---

## Key Things VPC Does

| What | Why |
|------|-----|
| **Connects your resources** | Your VMs, databases, storage can all talk to each other |
| **Keeps things secure** | Firewall rules block bad traffic |
| **Works worldwide** | Your network spreads across multiple countries |

---

## Subnets (Simple Zones)

**Subnet** = A section of your VPC in one region

- Each subnet is in **ONE region** (like Asia or USA)
- You can have **multiple VMs** in same subnet even if they're in different zones
- You can **grow the subnet** later without stopping your VMs ✅

**Example:**
```
My VPC Network:
├─ Asia Subnet (has 2 VMs)
└─ USA Subnet (has 1 VM)

All 3 VMs can talk to each other!
```

---

## Firewall Rules (Security Guards)

**Firewall** = Decides what traffic is allowed in/out

```
🚗 Traffic arrives
  ↓
🛂 Check firewall rule
  ↓
✅ Matches rule? → Let it in
❌ No rule? → Block it
```

**Common Rules:**
- Allow port 80 (web)
- Allow port 443 (secure web)
- Allow port 22 (SSH access)
- Block everything else

---

## Routes (Traffic Directions)

**Route** = Tells data where to go

Example: "If data goes to office network (192.168.0.0), send it through VPN"

---

## Multi-Region (Global Network)

**Why have servers in multiple regions?**

✅ **Speed** - Users get served from nearest location  
✅ **Safety** - If one region breaks, others keep working  

---

## Quick Setup Example

```
Step 1: Create VPC
Step 2: Add subnets (Asia + USA)
Step 3: Add VMs
Step 4: Set firewall rules (allow HTTP/HTTPS)
Step 5: Ready to use! 🎉
```

---

## Remember

- **VPC** = Your private cloud network
- **Subnet** = Part of VPC in one region
- **Firewall** = Security rules
- **Routes** = Data directions
- **Global** = Works worldwide

google cloud iaas engine solution:
Compute engine:
can create n run virtual machines on google infrastructure
no upront investmesnts 
thousands of vitual cpu can run on system thats designed to be fast and to offer consistent performance
each vm contians the power ans functionalitu of a full fleges os
can be configured much like physical server.by specifying 
the amt of CPU power n mem needed the amt n type of storage needed n os

Virtual machine: can be created using google cloud console the GC CLi or CE API which is webbased tool to manage gc projects n resources 
the instace can run linux n windows server images provided by google or any customized versions of these images
can build n run images of other os n flexibly reconfigure vms

a quick way to get started with gc is through cloud marketplace which offers solution from both google n third party vendors with these solutions theres no need to manually configure software vm instaces ,storage or n/w settings although many of them can be modified before launch if required 

most s/w packages are available at no additional charge beyond the normal fees
some cloud marketplace images chrage usage fees but they all show estimates of their monthly charges before theyre launched
for use of vm compute engine bills by the second with one min minimum n sustained use discounts start to apply automaticalls to vm the longer they run
ce also offers stable n predictbale workloads a specific amount of vcpus n memory can be purchased for up to 57% discount off of mormal prices in return for committing to usage term of one year or three years 
there are preemptible n spot vms 
spot vm more features no max runtime same pricing 
preemptible vms  less features runtime up to 24h same pricing 
ce doesnt require a particular option or machine type to gte high throughput between processing n persistent disks 
n finally we pay only for wt u need with custom machine types