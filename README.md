# Google-Cloud
Cloud training (Notes)
## Links: 
- https://www.nist.gov/
- https://www.youtube.com/watch?v=zDAYZU4A3w0
- https://cloud.google.com/
- https://en.wikipedia.org/wiki/Internet_Control_Message_Protocol
- https://en.wikipedia.org/wiki/Content_delivery_network
- https://en.wikipedia.org/wiki/Domain_Name_System
- https://en.wikipedia.org/wiki/Cloud_load_balancing
- https://cloud.google.com/docs/
- https://cloud.google.com/kubernetes-engine/
- https://www.theregister.co.uk/2014/05/23/google_containerization_two_billion/
- https://en.wikipedia.org/wiki/Linux_Foundation#Cloud_Native_Computing_Foundation
- 

## Certification Q's topic : (3 months of GCP handson is enough for clearing the certification)
All are MCQ's
- IAM 
- Compute Engine
- GKE
- App engine 
- network 7-8 Q's
- storage
- Container
- Images
- Machine Types 3-4 Q's

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
**********************************************************************************************************************************
## Day 2:
- By default when you create an instance on cloud you will get by default 2 IP's:
  - Internal IP : for private network
  - External IP : for outside world
- If external IP is changing every stop start of the instance then its an issue **hence we create a static external IP** and use it. (Check day 2 lab for creation of static ext IP)
- ***IP adress are regional components/objects***
- **IMP** If you have created an static external IP and you havent associated it with any intances then its FREE, as you are reserving an IP and not using it (and its not available in IP pool for GCP, and GCP has to buy a new IP to use and hence they will charge)
- **IMP** If you have created an static external IP and you have associated it with any intances then its not FREE

### GCP Persistent Disk
#### 1. Persistent Block storage: (PBS) Block level disks sitting on physical hard drives
- ***Disks are zonal components/objects***
- If you allocate 10GB for a disk and use only 1GB of space then we have to pay for 1GB only as all the cloud's have ***thin provisioning***
- In block level storage we cannot download or upload 
- In object storage we can upload and download
- the downloaded snapshot is in the cloud format (eg: GCP, azure format) we cannot use that downloaded snapshot anywhere.  

- **SNAPSHOT:**
- Its a **backup** of the disks which can be further used for restoring the disk data if there is a server failure or data loss **(disaster recover)**.
- snapshot of individual files is not possible hence we have to backup a disk alltogether

#### 2. Object Level Storage: (OLS) Whatever that is accessible from internet is Object level Storage.
- Examples of OLS is iCloud, google drive, etc 
- Google cloud storage is the top used OLS.
- OLS is 10 times cheaper than PBS
- Uploading is free, but downloading is chargeable.
- Highly scaleable
- can be used for backup and archival

### DR(Disaster recovery) & HA(High Availibilty)
- whatever file is created in cloud, that data is replicated 3 times, this is auto backup taken by GCP
- Regional DR is the most preferred access options by companies. 
- 4 options of availibilty :
  - Multi regional
  - regional
  - Nearline 
  - Coldline (Cheapest)
- After 3 years the DR backup is deleted forever.

### GCP storage concepts
#### Buckets: (used majorly to take backup of)
- Its a container(folder) for objects (files)
- Buckets are global
- Keys: any object (file) stored in bucket is identified by unique identifier
- Operations allowed in bucket:
  - read
  - write
  - download
- Its an enterprise version of google drive
  
#### Object life cycle:
- You can create a cycle for an object where we can define after some no. of days move the object from one bucket to other.
- when you say buckets here its:   **(these are the stages of the objects storage with cost staring highest from top to bottom)**
  - Multi regional
  - regional
  - Nearline 
  - Coldline (Cheapest, but the retreival time is quite high)

#### Networks in GCP:
- GCP is nothing without VPC (virtual private cloud)
- CIDR (Classless Inter-Domain Routing)
- **Note: IMP there is a hard limit in GCP : you can create only 7000 IPs.**
- IGW (Internet gateway) : this is an door (switch) to your VPC to outside world. And this will be default present in VPC.
- **Routing**
- **Firewall**
  - Ingres : Incoming is restricted by default (incoming traffic) 
  - Egres : Outgoing is by default all allowed (outgoing traffic)
- **Subnet**
- 

### Day 2 Practicals:
#### 1. Creation of Linux OS system (VM instance with Linux OS)
  - Reset/restart and observe public IP **(Answer: No change in IPs after reset)**
  - reeboot and observe the IPs **(Answer: internal unchanged but external changed)**

#### 2. Create an external IP and assign it to your instances
  - In console **VPC Network -> External IP addresses->Reserve static IP**
  - You can assign it to any instance that you have created
  - assign it to the instance that you created (please note the Region in which your instance is created, that needs to be selected for IP creation as well, or else the instance wont be listed)
  - Now start stop the instance and the IP will not change as we have reserved the static ext IP.
  - ***This should be the case in production as we dont want ext IP to be changed on every restart of the instance)***
  
#### 3. Persistent Disks:
  - Create a server (create instance)
  - assign a storage (create a disk and assign it to instance)
  - do partitioning (eg: formatting) (commands : **fdisk -l, mkfs(create file system : in linux its ext(1/2/3), xfs - extended file system), df -h**)
  - mount it (eg: creation of drives in the storage - for human readable ) 
  
**Commands:**
````
Create a new server 
Check the disks (This is OS disk)

  fdisk -l
  
Now create a new 10GB persistent disk and assign it to 
    5  fdisk /dev/sdb
    6  fdisk -l
    7  clear
    8  mkdir /tradereporting
    9  fdisk -l
   10  mkfs /dev/sdb
   11  df -h
   12  mount /dev/sdb /tradereporting/
   13  df -h
   14  clear
   15  df -h
   16  mount
   17  clear
   18  df -h
   19  mount
   20  cear
   21  clear
   22  history
````
  ##### output
```` root@day2instance:~# fdisk -l
Disk /dev/sda: 10 GiB, 10737418240 bytes, 20971520 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disklabel type: dos
Disk identifier: 0x8eb647e3

Device     Boot Start      End  Sectors Size Id Type
/dev/sda1  *     2048 20971486 20969439  10G 83 Linux
root@day2instance:~# fdisk -l
Disk /dev/sda: 10 GiB, 10737418240 bytes, 20971520 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disklabel type: dos
Disk identifier: 0x8eb647e3

Device     Boot Start      End  Sectors Size Id Type
/dev/sda1  *     2048 20971486 20969439  10G 83 Linux


Disk /dev/sdb: 10 GiB, 10737418240 bytes, 20971520 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
````
### 4. Buckets
- Create a bucket
- rename 
- delete

*********************************************************************************************************************
## Day 3 (Networks)
- **VPC**
  - Can be created in 2 ways: 
    - Custom  (selecting the regions u need)
    - Auto (selects all the regions by default)
    **IMP*: You can convert auto to custom VPC but not vice-versa
- When we create 4 subnets then we will be having 5 routings automatically (4 for subnets and 1 for internet)
- 4 **firewall** rules automatically get created:
  - ssh
  - rdp
  - icmp
  - allow all
  
- We can create **VPC** in 2 ways:
  - Multiregional (across regions)
  - Regional (confirned within region)
  
- **Subnet:**
  - Cloud reserves first 2 and last 3 ips i.e. 10.10.0.0, 10.10.0.1, 10.10.0.253, 10.10.0.254, 10.10.0.255 (which are local gateways)
  
- **VPC Peering:**
  - used to pair 2 VPC's (note: create 2 distinct subnets )

- **GKE:**
  - Google Kubernetes Engine is a powerful cluster manager and orchestration system for running your Docker containers. Set up a cluster in minutes.
  - Kubernetes is an **orchestration** over container
  - here orchestration means cloud of containers
  - Kubernetes is used to manage containers
  - less on investments (no investments on VM required)
  - 
  
### Day 3 Practicals:
- Create VPC: Networks -> VPC networks
- VPC peering
- GKE 
  -  Create a cluster : Kubernetes Engine -> Create cluster (2nodes; zonal)
  - Connect to cluster via shell
  - Enter the by default command which is prompted after opening the shell
  - run command ```` kubectl run <yourAppName> --image=httpd````
  - this command will deploy httpd image on one container in kubernetes
  - open the image in **workloads** and click on option **Expose** (this will expose your image to outside world)
  - once done: goto **workloads** open your deployed image and in **services** section (last one) click on the **endpoints** : that is the endpoint of your url.
