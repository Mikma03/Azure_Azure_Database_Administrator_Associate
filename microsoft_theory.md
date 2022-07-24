
<!-- TOC -->

- [Exam DP-300: Administering Relational Databases on Microsoft Azure](#exam-dp-300-administering-relational-databases-on-microsoft-azure)
  - [Introduction to Azure database administration](#introduction-to-azure-database-administration)
    - [Prepare to maintain SQL databases on Azure](#prepare-to-maintain-sql-databases-on-azure)
  - [Plan and implement data platform resources](#plan-and-implement-data-platform-resources)
    - [Deploy IaaS solutions with Azure SQL](#deploy-iaas-solutions-with-azure-sql)

<!-- /TOC -->
# Exam DP-300: Administering Relational Databases on Microsoft Azure

Official landing page:

- https://docs.microsoft.com/pl-pl/certifications/exams/dp-300

## Introduction to Azure database administration

- https://docs.microsoft.com/en-us/learn/paths/introduction-to-azure-database-administration/

### Prepare to maintain SQL databases on Azure

- https://docs.microsoft.com/en-us/learn/modules/prepare-to-maintain-sql-databases-azure/2-describe-azure-data-platform-roles

**Azure Database Administrator:** Implements and manages the operational aspects of cloud-native and hybrid data platform solutions built on Microsoft Azure data services and Microsoft SQL Server. The Azure Database Administrator uses a variety of methods and tools to perform day-to-day operations, including applying knowledge of using T-SQL for administrative management purposes.

**Purchasing model:** SQL Database comes in two main purchasing models: vCore-based model and DTU-based model. Each purchasing model offers the following service tiers

[Troubleshoot transient connection errors in SQL Database and SQL Managed Instance](https://docs.microsoft.com/en-us/azure/azure-sql/database/troubleshoot-common-connectivity-issues?view=azuresql)

    Azure SQL Managed Instance doesn't support DTU-based purchasing model.

**Serverless compute tier**

The auto-pause delay feature allows you to define the period of time the database will be inactive before it is automatically paused. The auto-pause delay feature can be set up from 1 hour to seven days. Alternatively, auto-pause delay feature can be disabled.

**Elastic pool**

Elastic pools allow you to allocate storage and compute resources to a group of databases, rather than having to manage resources for each database individually. Additionally, elastic pools are easier to scale than single databases, where scaling individual databases is no longer needed due to changes made to the elastic pool.

Elastic pools provide a cost-effective solution for software as a service application model, since resources are shared between all databases. You can configure resources based either on the DTU-based purchasing model or the vCore-based purchasing model.

**Continuous backup**

With SQL Database, you can increase administration efficiency by knowing that databases are backed up regularly, and that they are continuously copied to a read-access geo-redundant storage (RA-GRS).

Full backups are performed every week, differential backups every 12 to 24 hours, and transaction log backups every 5 to 10 minutes.

[Automated backups - Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/automated-backups-overview?tabs=single-database&view=azuresql)

    Azure SQL Managed Instance doesn't support elastic queries.

    Azure SQL Managed Instance doesn't support Data Sync feature.

[Tutorial: Set up SQL Data Sync between databases in Azure SQL Database and SQL Server](https://docs.microsoft.com/en-us/azure/azure-sql/database/sql-data-sync-sql-server-configure?view=azuresql)

**Explore Azure SQL Database Managed Instance**

For a complete list of the features available on Azure SQL Managed Instance, see 

[Features of SQL Database and SQL Managed Instance](https://docs.microsoft.com/en-us/azure/azure-sql/database/features-comparison?view=azuresql)

[License Mobility through Software Assurance on Azure](https://azure.microsoft.com/pl-pl/pricing/license-mobility/)

**Backup and restore**

Automated database backup provides a fully managed backup service that takes full, differential, and log backups regularly for both SQL Managed Instance and SQL Database offerings. Automated backups are geo-redundant, and replicated to a paired-region automatically, which protects your data against localized outages in the primary region.

Similarly, SQL Managed Instance allows easy migration of existing applications, enabling restores from on-premises backups.

There are some important considerations when running backup and restore operations on SQL Managed Instance databases:

- It isn't possible to overwrite an existing database during the restore process. Before restoring a database, you must ensure that it doesn't exist.

- For SQL Managed Instance, backups can only be restored to another managed instance. It isn't possible to restore a managed instance database backup to a SQL Server running on a virtual machine or SQL Database.

- Copy-only backup to Azure blob storage is available for SQL Managed Instance. SQL Database doesn't support this feature.

[Automated backups - Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/automated-backups-overview?view=azuresql)

    The auto-failover groups feature is supported on both SQL Managed Instance and SQL Database.

**Machine Learning Services
**
Machine Learning Services provides machine learning operations within your relational database structure. This feature supports Python and R packages, ideal for high-intensive predictive capabilities. This option is available on SQL Managed Instance, SQL Server on Azure virtual machine, and on-premises SQL Server.

[PREDICT (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/queries/predict-transact-sql?view=sql-server-ver16)

    SQL Database doesn't support Machine Learning Services feature.


## Plan and implement data platform resources

- https://docs.microsoft.com/en-us/learn/paths/plan-implement-data-platform-resources/

### Deploy IaaS solutions with Azure SQL

- https://docs.microsoft.com/en-us/learn/modules/deploy-iaas-solutions-with-azure-sql/

**Infrastructure as a Service (IaaS)** 

Allows the administrator to have more granular access over specific settings of the underlying infrastructure than the other Azure offerings. While the Azure platform manages the underlying server and network hardware, you still have access to the virtual storage, virtual networking configuration, and any additional software you might install within the virtual machine. This includes Microsoft SQL Server.

**Virtual machine families**

When deploying to an Azure virtual machine, there are several series, or “families”, of virtual machine sizes that can be selected. Each series is a combination of memory, CPU, and storage that meets certain requirements. For example, the series that are compute optimized have a higher CPU to memory ratio. Having multiple options allows you to select an appropriate hardware configuration for the expected workload. 

[General purpose ](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-general)- These VMs provide a balanced ratio of CPU to memory. This VM class is ideal for testing and development, small to medium-sized database servers, and web servers with a low to medium amount of traffic.

[Compute optimized](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-compute) - Compute optimized VMs have a high CPU-to-memory ratio and are good for web servers with a medium amount of traffic, network appliances, batch processes, and application servers. These VMs can also support machine learning workloads that can't benefit from GPU-based VMs.

[Memory optimized](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-memory) - These VMs provide high memory-to-CPU ratio. These VMs cover a broad range of CPU and memory options (all the way up to 4 TB of RAM) and are well suited for most database workloads.

[Storage optimized](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-storage) - Storage optimized VMs provide fast, local, NVMe storage that is ephemeral. They are good candidates for scale-out data workloads such as Cassandra. It is possible to use them with SQL Server, however since the storage is ephemeral, you need to ensure you configure data protection using a feature like Always On Availability Groups or Log Shipping.

[GPU](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-gpu) - Azure VMs with GPUs are targeted at two main types of workloads—naturally graphics processing operations like video rendering and processing, but also massively parallel machine learning workloads that can take advantage of GPUs.

[High performance compute](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-hpc) - High Performance Compute workloads support applications that can scale horizontally to thousands of CPU cores. This support is provided by high-performance CPU and remote direct memory access (RDMA) networking that provides low latency communications between VMs.


**Azure Arc enabled SQL Servers**

Having Azure Arc enabled SQL Servers extends and centralizes Azure management services to SQL Server instances hosted on-premises, in your data centers, on the edge, and in multi-cloud environments. In this hybrid scenario, Azure Arc enables the inventory of all registered SQL Server deployments and assesses their configurations, usage patterns, and security to provide actions and recommendations based on best practices. By using Azure Arc enabled SQL Servers, you gain the benefits of centralized server management. You also get Azure Defender real-time security alerts and vulnerability reporting on both on-premises SQL Servers and their host operating systems.

**Security considerations**

When deploying a hybrid SQL solution, all core infrastructure, such as Active Directory and DNS, must exist on-premises and in Azure. In addition, secure two-way communication must exist between the on-premises network and Azure. This secured communication can take the form of a site-to-site (S2S) VPN or a dedicated ExpressRoute tunnel. When evaluating different connectivity methods, it's vital to determine the amount of latency acceptable for your organization. Regardless of the solution chosen, network security must also be at the forefront of the implementation.

**Storage considerations**

SQL Server requires good storage performance to deliver robust application performance, whether it be an on-premises instance or installed in an Azure VM. Azure provides a wide variety of storage solutions to meet the needs of your workload. While Azure offers various types of storage (blob, file, queue, table) in most cases SQL Server workloads will use Azure managed disks. The exceptions are that a Failover Cluster Instance can be built on file storage and backups will use blob storage. Azure-managed disks act as a block-level storage device that is presented to your Azure VM. Managed disks offer a number of benefits including 99.999% availability, scalable deployment (you can have up to 50,000 VM disks per subscription per region), and integration with availability sets and zones to offer higher levels of resiliency in case of failure.

**Each VM will have at least two disks associated with it:**

- Operating System disk – Each virtual machine will require an operating system disk that contains the boot volume. This disk would be the C: drive in the case of a Windows platform virtual machine, or /dev/sda1 on Linux. The operating system will be automatically installed on the operating system disk.

- Temporary disk – Each virtual machine will include one disk used for temporary storage. This storage is intended to be used for data that does not need to be durable, such as page files or swap files. Because the disk is temporary, you should not use it for storing any critical information like database or transaction log files as they will be lost during maintenance or a reboot of the virtual machine. This drive will be mounted as D:\ on Windows, and /dev/sdb1 on Linux.

**Additionally, you can and should add additional data disks to your Azure VMs running SQL Server.**

- Data disks – The term data disk is used in the Azure portal, but in practice these are just additional managed disks added to a VM. These disks can be pooled to increase the available IOPs and storage capacity, using Storage Spaces on Windows or Logical Volume Management on Linux.

**Table partitioning**

Table partitioning provides many benefits, but often times this strategy is only considered when the table becomes large enough that starts compromising query performance. Identifying which tables are candidates for table partitioning is a good practice that could lead to less disruptions and interventions. When you filter your data using your partition column, only a subset of the data is accessed, not the entire table. Similarly, maintenance operations on a partitioned table will reduce maintenance duration, for example, by compressing specific data in a particular partition or rebuilding specific partitions of an index.

There are four main steps required when defining a table partition:

- The filegroups creation, which defines the files involved when the partitions are created.
- The partition function creation, which defines the partition rules based on the specified column.
- The partition scheme creation, which defines the filegroup of each partition.
- The table to be partitioned.

[Checklist: Best practices for SQL Server on Azure VMs](https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/performance-guidelines-best-practices-checklist?view=azuresql)

**Always On availability groups (AG)**

Always On availability groups can be implemented between two or more (up to a maximum of nine) SQL Server instances running on Azure virtual machines or across an on-premises data center and Azure. 