# Google-Cloud
Cloud training (Notes)

## Day 1: 
- Everything as a service is CLOUD. *(Platform which provides a service)*
  Example: Gmail, Orkut, whatsapp, etc.

- IBM Watson is another service by IBM which was started in 1980 and it took them 35 years. 
  - It uses machine learning (ML) and AI and IBM uses Watson for doing every stuff. 

- **NIST** (National Institute of Standard and Technology) - enforced by the US (https://www.nist.gov/)
  - IAAS, PAAS and SAAS these 3 service models are must as per NIST policy/benchmarks
  
- **Public** and **Private** cloud providers (GCP, Azure, AWS)

### Public Cloud: 
- providing the service publically

### Private Cloud:
- Examples of prrivate cloud : 
  - Openstack 
  - Azure stack by Microsoft
  - VM ware cloud (not a true private cloud)

### Hybrid Cloud: 
  - When you use more than one cloud then its hybrid cloud

### Community CLoud:
  - Company investing in cloud for their own purpose (kind of Private)

### 5 Essential characteristics of cloud:
  - Self service
  - Network connectivity
  - Resource pooling
  - Scaling
  - Measuribility (Monitoring)
  
- AWS has its own linux **(AWS Linux)** (This saves the licensing cost)
- *AWS provides services to 199 out of 237 countries.*
- *Google has presence in 33 countries and data centers in more than 100 countries.*

### ******************************** GCP (Google Cloud Platform) ********************************
- Group of services provided by Google 
- Rent infra and discard after use, ***pay per second***
- **Core benefits:**
  - Low cost
  - Instant elasticity
  - Scalbility
  - Multiple OS's
  - Multiple storage options
  - Secure
- **Smart Datacenters** by Google:
  - Cooling system
  - Eco friendly data centers (use of wind mills, water to create energies)
  - Storage of data centers in oceans (Azure has done this)
  
#### All about GCP:
- Google create their own h/w and developing their own data centers on that H/W
- Google is working on containers since past 12 years
- Youtube, gmail all are hosted on containers and not VM's ; These containers resume in 10secs if in case of any shutdown unoike VM's
- **Note: Refer the link https://www.youtube.com/watch?v=zDAYZU4A3w0 **
- Regions(geographical location [specific KMs]) and zones (physical DC's)
- Read about **global networks** in google
- in google we can have 3 zones per region
- default no. of zones should be always greater than 1
- google has 55 DC's overall

#### GCP cloud computing platform
- Divided in 2 parts/channels:
  - Cloud architecture
  - Data analytics

#### GCP resources (refer diagram in presentation)
- Global 
- Regional
- Zonal

#### GCP projects
- Project is an unique entity 
- consider GCP as environment and projects as racks 
- one rack (project) cannot communicate with each other
- billing will happen based on project (and is tracked by Google based in project ID)

#### GCP Services
- Compute engine (IaaS)
- Kubernetes engine (C{ontainer}aaS)
- App engine (PaaS)
- Cloud functions (SaaS)

#### Link : [https://cloud.google.com/about/locations/#regions-tab]

### Day 1 Practicals: 
- Link : https://cloud.google.com/
- Create cloud account
- **Important note:** always delete the resource which you dont use.
- Console: Its the GCP dashboard
- Cloud Shell: google cloud shell: main use is to execute commands and perform things. Eg: run a python script
- In **new instance**:  
  - Machine type option is no. of CPU's (the ratio is 1:4 CPU:RAM)
  - **Shared CPU** : shared with multiple instances (on demand CPU is assigned by Google automatically) --> For testing/practice always use this shared CPU
  1. Create a project
  2. In Compute Engine -> VM Instances (create VM instance - select shared CPU)
