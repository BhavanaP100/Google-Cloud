# 🌐 Virtual Private Cloud (VPC)

## What is Virtual Private Cloud (VPC)?

**VPC:** A secure, individual, private cloud model hosted within a public cloud provider.

On VPC, customers can run code, host websites, store data, and anything else that can be done on a private cloud. A virtual private cloud is hosted remotely by a public cloud provider. This means VPC combines the scalability and convenience of public cloud computing.

---

## Key Points

✅ **Connects resources** - VMs talk to each other  
✅ **Secure** - Firewall protects traffic  
✅ **Global** - Works across regions  
✅ **Subnets** - Region-specific sections, can expand IP range anytime without stopping VMs  
✅ **Multi-zone** - Same subnet can have VMs in different zones  

---

# 🖥️ Compute Engine

## What is Google Cloud Compute Engine?

**Compute Engine:** Google Cloud's Infrastructure as a Service (IaaS) solution that allows you to create and run virtual machines on Google's infrastructure.

You can create and run virtual machines on Google infrastructure with no upfront investments. Thousands of virtual CPUs can run on a system designed for fast and consistent performance. Each VM is like a full operating system where you can specify CPU power, memory, storage type, and operating system.

---

## Creating VMs - Simple Explanation

**What is a VM?** = A computer that doesn't physically exist, runs on Google's servers

**How to create:**
- **Google Cloud Console** = Click buttons (easy)
- **Google Cloud CLI** = Type commands (advanced)
- **Compute Engine API** = Automate it

**OS Options:**
- **Linux** = Free, lightweight for servers ✅
- **Windows Server** = Paid, if you need Windows
- **Custom** = Build your own

**Quick Start:** Cloud Marketplace has pre-configured packages ready to use (most are free!)

---

## Pricing - Pay by the Second ⏱️

💰 **Per-second billing** - Run 5.5 minutes = pay only 5.5 minutes (NOT full hour!)

**Save money:**
- **Sustained-use discount** = Automatic when you keep VM running longer
- **Commitment discount** = Up to 57% off if you promise 1-3 years usage

---

## Special Budget VMs

| Type | Price | Runtime | Best For |
|------|-------|---------|----------|
| **Spot VM** | Cheap | No limit | Non-urgent tasks |
| **Preemptible VM** | Super cheap | Max 24 hours | Short experiments |

---

## VM Features

✅ **High throughput** - Fast processing  
✅ **Persistent disks** - Fast storage stays with VM  
✅ **Custom machine types** - Pick exact CPU + memory you need  
✅ **Pay for what you use** - No waste  

---

## Remember

- **Compute Engine** = Renting virtual computers
- **VM** = Virtual machine (computer in cloud)
- **OS** = Operating system (Linux/Windows)
- **Billing** = Per second (very cheap!)
- **Spot/Preemptible** = Budget options
- **Marketplace** = Ready-to-use solutions

-------

to do this ce has a feature called autoscaling where vms can be added to or subtracted from an application based on load metrics.
the other part of making that work is balancing the incoming traffic among the vms.
vpc supports several different kinds of load balancing with ce we can configure very large vms which are great for workloads such as in memory databases n cpu intensive analytics but most gc customers start off with scaling out not up 
The maximum number of cpus per vm is tied to its "machine family" n is also tied to it machine family n constrained by users quota

compatability Features of vpc :
vpc routing tables are built in 
no router provision or manageing
fprward traffic from one instance to another across subnetsor btw google cloud zones
without requiring external ip adress

Firewall:
no router provisioning or managing 
restrocr acess to instances
rules can be defined through netwrok tags
for eg u can tag all web servers with say web and set firewalls rule saying that traffic on ports 80 or 443 is allowed into all vms with the  web tag , no matter what their IP adress happens to be

vpc belong to google cloud projects but wt if ur company has several gc projects n vpx need to talk to each other?
with vox peering a relationship btw 2 vpcs can be established to exchange traffic 
alternatively to use full power of iam to control who n what in one project can interact with a vpc in another u can configure shared vpc 
---------------

cloud load balancing :
how do ur customers get to ur application when it right be provided by 4 vms one moment and by 40 vms at another ?
the cloud load balancing is used to distribute user traffic across multiple instances of an application by spreading the load , load balancing reduces the risk that app experience performance issues 
cloud load balancing is fully distributed , s/w -defined , managed service for all traffic 
u can put cloud load balancing in front of all of ur traffic
HTTP(s)
TCP traffic
SSL traffic
UDP traffic
cloud load balancing provides cross-region load balancing ,including automatic multi region failover which gently moves traffic in fraction if backends become unhelathy
cloud loadbalncing reacts quickly to changes in users , traffic , n/w , backend health, n other related conditions 
no 'pre -warming is required for anticipated spikes int traffic 

gc offers a range of load balacing solution that can be classified based on OSI model layer they operate at their specific fucntionalities 
application load balancer operate at the application layer n r designed to handle http  n https traffic,making them ideal for web applications n services that require advanced features like content based routing n SSL/TLS TERMINATIOn. application load balancers operate as reverse proxies,
distibuting incoming traffic across mulyiple backend instances based on rules u define they r highly flexible n can be configured for both internet facing n internal applications 

n/w load balancers operate at the transport layer n efficiently handle TCP, UDP ,n other IP protcols.
they can befurther classified into 2 types:
proxy n/w load balancers also fucntion as reverse procies,terminating n esatablishing new ones to backend services thwy offer advanced traffic management capablities n support bacekend loctedboth on premises n in various cloud environments.
unlike proxy n/w load balancers passthrough n/w load balancers do not modufify or terminate conncetions instead they directly forward traffic to the bakend while preserving the original source of ip adress
-----------
cloud dns n cloud cdn 
one of the most famous free google services is 8.8.8.8,which provide public domain name service to the world 
DNS is what translates internet hostnames to addresses 
google has higly developed dns infrastructure that makes 8.8.8.8 available so that everyone can take advantage of it 
google cloud offers cloud dns to help worlf find them 
its managed DNS service that runs on the same infrastructure on t=google
low latency ,high avalialbility , n cost efficitvwness 
the dns information u publish is served fm redundant loaction around the world
cloud DNS is programmble,u van publisj n manage millions of dns zones n records using the google cloud console the command line interface or the api
google also has a global system of edge cches edge caching refers to the use of caching servers to store content closer to end users
u can usethis sys to accelerate content delivery in ur application this means ur customers will exp lowwer n/w latency ,  the origin of ur content will exp reduced load , save money after an app looad balancer is set up  enabled with single checkbox there many other cdn available out there of course 