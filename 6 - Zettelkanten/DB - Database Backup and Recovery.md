
2024-08-11 19:39

Status:

Tags: #UOM #L2S2-S4 #DB 


# DB - Database Backup and Recovery


## What is backup and recovery?
Backup and recovery is the process of duplicating data and storing it in a secure place in case of loss or damage, and then restoring that data to a location—the original one or a safe alternative—so it can be used again in operations. Ideally, this backup copy (often called a snapshot) is immutable—meaning it cannot be altered after it is created to protect against mutations such as ransomware. Backup and recovery is also a category of onsite and cloud-based technology solutions that automate and support this process, enabling organizations to protect and retain their data for business and compliance reasons.

## What are the 3 types of backups?
Backups are often bucketed into three categories:

**Full backups** – Like filling up an extra tire at the service station, think of this process as pumping all of the data stored on a production system into a backup system for safekeeping. Full backups protect every bit of data from a single server, database, virtual machine (VM), or data source connected to the network. These backups can take many hours, even days, depending on the amount of data being saved. The more modern a data management solution is, the fewer full backups it must perform, and when it does, the faster it goes.

**Incremental backups** – Think of incremental backups as adding just a little more air each time you revisit the station—just in case—so you’re always ready to replace your tire. An incremental backup captures only new data since the last full incremental was performed. However, a full backup is required before a backup solution can perform its first incremental backup. Then it can automatically do them based on the last incremental taken. 

**Differential backups** – Like incremental backups, these add more air but the delta is from the last full backup, not the last incremental. Think of this backup as what’s different from the last time you even filled the tire with air. Again, this can only happen if a full backup has been performed first. Organizations typically establish policies about how much data and when incremental or differential backups should occur.


## **Full Backup**

A **Full Backup** is a complete copy of your entire database. It includes all the data, objects, and system tables. This type of backup is like taking a snapshot of your database at a specific point in time.

### **How Full Backups Work**

1. **Initial Full Backup**: A complete copy of the database is made.
2. **Subsequent Full Backups**: Each full backup is an independent copy of the entire database.

### **Example Scenario**

Imagine you have a library with 1000 books. Here’s how a full backup would work:

- **Sunday**: You take a full backup (photograph) of the entire library, capturing all 1000 books.
- **Monday**: 10 new books are added to the library. You take another full backup, capturing all 1010 books.
- **Tuesday**: 5 more books are added. You take another full backup, capturing all 1015 books.

Each full backup is a complete and independent copy of the library at that specific point in time.

### **Advantages of Full Backups**

- **Complete Data Protection**: Since it includes everything, you have a complete copy of your data.
- **Fast Recovery**: Restoring from a full backup is straightforward because it contains all the data in one set.
- **Simplicity**: Easy to manage and understand, as each backup is a complete snapshot.

### **Disadvantages of Full Backups**

- **Time-Consuming**: Creating a full backup can take a long time, especially for large databases.
- **Storage Space**: Requires a lot of storage space since each backup is a complete copy of the database.
- **Bandwidth Usage**: Uses a lot of network bandwidth if backups are transferred over a network.

### **Restoration Process**

To restore the library to its state on any given day, you simply use the full backup from that day. For example, to restore the library to its state on Tuesday, you would use the full backup taken on Tuesday.

### **Summary**

- **Full Backup**: A complete snapshot of the entire database.
- **Efficient for Recovery**: Fast and straightforward to restore.
- **Storage Intensive**: Requires significant storage space and time to create.



## **Incremental Backup**

An **Incremental Backup** only includes the data that has changed since the last backup, whether it was a full backup or another incremental backup. This method is efficient in terms of time and storage space.

**Example**: Imagine you have a library with 1000 books. You take a full backup (photograph) of the library on Sunday. On Monday, 10 new books are added. An incremental backup on Monday will only include these 10 new books. On Tuesday, 5 more books are added. The incremental backup on Tuesday will only include these 5 new books. This process continues, capturing only the changes made since the last backup.

- **When to Use**: Often used for daily backups to minimize storage and time.
- **Advantages**: Faster and smaller than full and differential backups.
- **Disadvantages**: Restoring can be slower because you need the last full backup and all subsequent incremental backups.

### **How Incremental Backups Work**

1. **Initial Full Backup**: A complete copy of the database is made (e.g., on Sunday).
2. **First Incremental Backup**: Only the changes made since the full backup are copied (e.g., on Monday).
3. **Subsequent Incremental Backups**: Each backup only includes changes since the last incremental backup (e.g., Tuesday, Wednesday, etc.).

### **Example Scenario**

- **Sunday**: Full backup of the library (1000 books).
- **Monday**: 10 new books added. Incremental backup includes these 10 books.
- **Tuesday**: 5 more books added. Incremental backup includes these 5 books.
- **Wednesday**: 15 books borrowed. Incremental backup includes the changes (books borrowed).

### **Restoration Process**

To restore the library to its state on Wednesday:

1. **Full Backup**: Use the full backup from Sunday.
2. **Incremental Backups**: Apply the incremental backups from Monday, Tuesday, and Wednesday.

This ensures that all changes are captured and the library is restored to its exact state on Wednesday.

### **Summary**

- **Incremental Backup**: Only backs up changes since the last backup.
- **Efficient**: Saves time and storage space.
- **Restoration**: Requires the last full backup and all subsequent incremental backups.


## **Differential Backup**

A **Differential Backup** includes all the data that has changed since the last full backup. It accumulates changes over time, making it larger with each backup until the next full backup is taken.

**Example**: Imagine you have a library with 1000 books. You take a full backup (photograph) of the library on Sunday. On Monday, 10 new books are added. A differential backup on Monday will include these 10 new books. On Tuesday, 5 more books are added. The differential backup on Tuesday will include the 10 books from Monday plus the 5 new books from Tuesday, totaling 15 books. This process continues, capturing all changes since the last full backup.

### **How Differential Backups Work**

1. **Initial Full Backup**: A complete copy of the database is made (e.g., on Sunday).
2. **First Differential Backup**: Only the changes made since the full backup are copied (e.g., on Monday).
3. **Subsequent Differential Backups**: Each backup includes all changes made since the last full backup (e.g., Tuesday, Wednesday, etc.).

### **Example Scenario**

- **Sunday**: Full backup of the library (1000 books).
- **Monday**: 10 new books added. Differential backup includes these 10 books.
- **Tuesday**: 5 more books added. Differential backup includes the 10 books from Monday and the 5 new books from Tuesday (total 15 books).
- **Wednesday**: 15 books borrowed. Differential backup includes the 10 books from Monday, the 5 books from Tuesday, and the 15 books borrowed on Wednesday (total 30 changes).

### **Restoration Process**

To restore the library to its state on Wednesday:

1. **Full Backup**: Use the full backup from Sunday.
2. **Latest Differential Backup**: Apply the differential backup from Wednesday, which includes all changes since Sunday.

This ensures that all changes are captured and the library is restored to its exact state on Wednesday.

### **Advantages of Differential Backups**

- **Faster Backup Times**: Since you’re not copying everything, differential backups are usually quicker than full backups.
- **Quicker Restores**: Restoring data from a differential backup is faster than restoring from incremental backups because you only need the last full backup and the latest differential backup.

### **Disadvantages of Differential Backups**

- **More Storage Space**: Differential backups take up more space than incremental backups since each one contains all the changes since the last full backup.

### **Summary**

- **Differential Backup**: Backs up all changes since the last full backup.
- **Efficient**: Faster than full backups and simpler to restore than incremental backups.
- **Restoration**: Requires the last full backup and the latest differential backup.



## What is the difference between backup and recovery?
The key difference between backup and recovery is that the backup process is how you save and protect your production data and safely store it away so you have it for a later time, when you might need to use it.

Recovery is the process whereby you retrieve and restore that backup data to your production systems to avoid downtime.

Reliable backups and fast recovery together ensure business continuity and business resilience.

## What are the types of data recovery?
The amount of data organizations create, capture, and store has skyrocketed over the last decade. And analysts anticipate the amount of new data generated will grow at more than 50% compounded annually.

Because enterprises and people are storing data in more places, new categories of backup data recovery have emerged. These include:

Granular recovery of files, folders and objects – Also known as file-level or object-level recovery, this is the process of quickly getting back one or just a few specific data sets from among many volumes.
Instant mass restore – This process allows IT staff to recover not just files but hundreds of virtual machines (VMs) instantly, at scale, to any point in time, saving time and resources.
Volume recovery – A process teams that need to recover an unlimited number of VMs at the same time used for faster recovery; for example, all VMs belonging to an application group.
Virtual Machine Disk (VMDK) recovery – This recovery process ensures all data and apps on a VM are restored quickly.
Bare machine recovery – Restoring an entire operating system (software, apps, and data) in one process.
Instant volume mounts – Teams can save time using a backup solution as a target to restore an entire volume to a Windows VM.
Instant restores of VMs – This process restores a large number of VMs to any previous recovery point with backup copies fully hydrated and available immediately.
What is disaster recovery backup?
For enterprises, a disaster is when a catastrophic event negatively impacts your people and/or your data. The event can be natural—a hurricane taking down a data center, for example—or human-made, such as a ransomware attack. Regardless of whether disasters are due to human error, hardware failure, malicious attacks, or natural events, the result is the same—data corruption or lost data that makes it difficult to ensure business continuity.

Disaster recovery is the process your IT organization goes through to restore data. Increasingly, organizations are setting aside a complete or full backup of entire environments—either on-premises or in the public cloud—to ensure all of their data can be made available quickly in the event of a catastrophe. Having a way to quickly recover lost or damaged data is crucial for business continuity, and using cloud storage in disaster recovery planning is ideal for backing up essential business data.

## What types of data sources typically need to be recovered?
All of the data sources that your organization protects may at some time need to be recovered due to a data loss event. These include:

VMs (VMware, Microsoft, Nutanix)
Physical servers (Windows, Linux)
Databases (RDBMs) and Distributed Databases (NoSQL, Hadoop, Mongo, Apache, etc.)
Files (NAS)
Containers (e.g. Kubernetes)
Applications (Microsoft Exchange, SAP HANA)
SaaS applications (Microsoft 365, Salesforce)
Primary storage
Mainframes

## Why do you need a data backup and disaster recovery plan?
Data is essential to organizations of all types and sizes. You need a robust data backup and disaster recovery plan because it provides a roadmap for the people responsible for taking charge in a disaster scenario to know who is doing what and in what sequence to restore operational functionality. Your DR plan should include both people and processes, serving as a guide for employees to follow as they bring your business back up.

A robust data backup and disaster recovery plan should also ensure that your data is always protected—as and after you move it from day-to-day production systems for short—and long-term retention. With the best backup and disaster recovery plan, you will always have your data readily available should you need it.

Imagine if the data needed to operate your business, department, or agency was unavailable, even for a few minutes, never mind hours, days, or weeks. Customers would be unhappy. Employees would be, too. And in the case of ransomware, your entire business might even cease to exist. Effective backup and recovery of important data prevents all of these scenarios.

## Is data deduplication important in backups?
Yes, data deduplication is absolutely important in backups. Here’s why. Data is growing exponentially and organizations are retaining more data—for marketing, compliance, and more—than ever. Because of this, IT teams need to deploy techniques that will help their organizations reduce data footprints, keeping costs lower.

Advanced data reduction through deduplication enables more data to fit into the same hardware space—helping to reduce cost.

The most powerful and flexible global deduplication architecture is variable-length data deduplication technology that spans an entire cluster across various data sources rather than simply a single node, resulting in significant savings across the entire storage footprint.

With variable-length deduplication, the size is not fixed. Instead, the algorithm divides the data into chunks of varying sizes based on the data characteristics. The chunks are cut in a data-dependent way that results in variable-sized chunks and greater data reduction than fixed-size deduplication. The efficiency benefit of variable-length deduplication compounds over time as additional data is retained.

Integrated data compression adds a boost. Compression works well on a single file, but across files, there is a need for some macro-level data compression. Why? Because when two identical copies of a file are stored, compression can individually compress the files while deduplication can completely eliminate the need to store any data for the second copy. So adding compression to the deduped data further reduces data size.

This works by finding small byte patterns common between the deduplicated blocks. Based on the type of data being ingested, compression can provide no benefit for encrypted or random data or up to 5–10x compression for common log files. Deduplication ratios for VMs, databases, and file shares belong somewhere belong between that range.

## Why is backup and recovery important?
Data powers your organization and your competitive advantage. That’s why backup and recovery is important. With a robust data backup and recovery strategy — and technology solution — in place, your organization can:

Prevent data loss – The fallout from lost or compromised data ranges from irritating to costly. Businesses can suffer financial penalties and loss of customer trust and brand reputation. The main role of backup and recovery is to preserve critical data in case of loss or damage.
Sustain operations – In the face of disaster—natural or manmade, including a ransomware attack — businesses keep functioning.
Maintain a good customer experience – Lost customer records create business challenges such as reduced customer satisfaction and revenue and non-compliance with regulations. Alternatively, rich, always-available customer datasets drive greater customer loyalty and, consequently, higher profits.
Keep employees productive – Effective data backup and recovery eliminates wasted time employees must spend rewriting reports, rekeying data, or recalculating spreadsheets when data and files go missing.
Retain historical records – Backing up data allows businesses to build corporate archives of their operations, and in some cases is mandated by industry or government regulations.
Satisfy auditors – Laws differ from one jurisdiction to another, but having important accounting and other financial records backed up, recoverable, and easily accessible for both tax reasons and audits is critical to business operations.
Achieve peace of mind – Whether a hurricane, cybercrime, or system failure, bad things can happen to even the most well-managed companies. Having a robust data backup and recovery strategy, supported by the right technology solution, means that your organization can be resilient and weather even the most difficult circumstances.
Modern, comprehensive backup and recovery versus traditional backup and recovery
Modern, Comprehensive Backup and Recovery	Traditional Backup and Recovery
Low (or no) capital costs. Modern backup solutions are typically a single platform with low or no on-prem infrastructure footprint, keeping backup and recovery costs low.	High capital costs. Often IT must cobble together multiple, costly infrastructure point products for data backup which raises costs.
Fast, accurate backups. Modern backup eliminates data silos and automates operations for faster, more accurate backups than traditional approaches.	Slow, error-prone backups. Traditional backup contributes to mass data fragmentation — having siloed data that requires manual operations and leads to greater backup errors than modern approaches.
Set and forget policies. Once IT staff creates and approves policies, they are easily and automatically added to data sources as servers join the network.	Tedious policy setting. IT staff must create and manage a unique policy for each data source as it is added to the network. And if a server is added without IT being notified, the business risks data not being backed up.
Instant and predictable recovery. Modern backup minimizes data loss and provides predictable recovery assurance with restores at scale, and to any point in time.	Unpredictable recovery. Traditional backup can be slow and error-prone, often bleeding into production time.
Unlocks business value through complete data visibility. Because there are no longer data silos and all backups are completed on one platform, IT can see and gain insights from all of enterprise data and apps.	No access to business insights because data is dark or hidden. Because backups are completed using many products and data can easily be lost, IT has dark data that makes it impossible to use for business insights.
Ransomware protection. Modern backups feature immutable snapshots and have minimal data center footprints, reducing attack surfaces.	Ransomware protection. Traditional backups do not include immutable snapshots and have large data center footprints, widening attack surfaces.
Cohesity’s modern approach to backup and recovery
The single biggest challenge with trying to put an enterprise-wide backup and recovery strategy in place is that data typically resides in numerous places: in on-premises systems, clouds, and at the edge. Mass data fragmentation from siloed hardware and software and incomplete visibility into enterprise data means that time that should be spent on business innovation is wasted managing and maintaining disconnected point solutions.

Cohesity provides a backup and recovery solution that converges multiple point products and backs up data whether it is stored on-prem, at the edge, or in the public cloud on a single multicloud data platform. By taking a complex operation and simplifying it for businesses, Cohesity ensures business continuity, minimizes data loss, and reduces the total cost of ownership (TCO).

As a Gartner Magic Quadrant Data Center Backup and Recovery Solutions, Cohesity’s business is the data business. Cohesity radically simplifies how organizations manage their data everywhere and derive more value from that data.

Organizations that choose Cohesity enjoy:

Simpler, centralized management of all backups across customer-managed and Cohesity-managed backup-as-a service environments
One platform to protect most traditional and modern, cloud-native data sources
Rapid recovery and reduced business downtime from ransomware with instant mass restore and granular search capabilities
A single platform that enables organizations to do more with their backup data while shrinking their data footprint for a strengthened security posture

The **3-2-1 Backup Strategy** is a widely recommended approach for ensuring data protection and recovery. Let’s break it down with a simple explanation and an example.

### **What is the 3-2-1 Backup Strategy?**

The 3-2-1 Backup Strategy involves:

1. **3 Copies of Your Data**: Keep three copies of your data.
2. **2 Different Media**: Store these copies on two different types of media.
3. **1 Off-site Copy**: Ensure one of these copies is stored off-site.

### **Why Use the 3-2-1 Backup Strategy?**

This strategy helps protect your data from various types of failures, such as hardware malfunctions, natural disasters, and human errors. By having multiple copies in different locations and on different media, you reduce the risk of losing all your data at once.

### **Illustration with an Example**

Imagine you have important family photos stored on your computer. Here’s how you would apply the 3-2-1 strategy:

1. **Three Copies of Your Data**:
    
    - **Original Copy**: The photos stored on your computer.
    - **First Backup Copy**: A copy of the photos on an external hard drive.
    - **Second Backup Copy**: Another copy of the photos stored in the cloud (e.g., using a service like Google Drive or Backblaze).
2. **Two Different Media**:
    
    - **Computer’s Internal Storage**: The original photos.
    - **External Hard Drive**: The first backup copy.
    - **Cloud Storage**: The second backup copy.
3. **One Off-site Copy**:
    
    - **Cloud Storage**: The copy stored in the cloud is off-site, meaning it’s not physically located in the same place as your computer and external hard drive.

### **Benefits of the 3-2-1 Backup Strategy**

- **Redundancy**: Multiple copies ensure that if one fails, you still have others.
- **Resilience**: Different media types protect against specific failures (e.g., hard drive crash, fire).
- **Recovery**: Off-site storage protects against local disasters (e.g., theft, flood).
# Reference