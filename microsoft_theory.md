
<!-- TOC -->

- [Exam DP-300: Administering Relational Databases on Microsoft Azure](#exam-dp-300-administering-relational-databases-on-microsoft-azure)
- [Introduction to Azure database administration](#introduction-to-azure-database-administration)
  - [Prepare to maintain SQL databases on Azure](#prepare-to-maintain-sql-databases-on-azure)
- [Plan and implement data platform resources](#plan-and-implement-data-platform-resources)
  - [Deploy IaaS solutions with Azure SQL](#deploy-iaas-solutions-with-azure-sql)
  - [Deploy PaaS solutions with Azure SQL](#deploy-paas-solutions-with-azure-sql)
  - [Evaluate strategies for migrating to Azure SQL](#evaluate-strategies-for-migrating-to-azure-sql)
  - [Migrate SQL workloads to Azure SQL Databases](#migrate-sql-workloads-to-azure-sql-databases)
  - [Migrate SQL workloads to Azure Managed Instances](#migrate-sql-workloads-to-azure-managed-instances)
- [Implement a secure environment for a database service](#implement-a-secure-environment-for-a-database-service)

<!-- /TOC -->
# Exam DP-300: Administering Relational Databases on Microsoft Azure

Official landing page:

- https://docs.microsoft.com/pl-pl/certifications/exams/dp-300

# Introduction to Azure database administration

- https://docs.microsoft.com/en-us/learn/paths/introduction-to-azure-database-administration/

## Prepare to maintain SQL databases on Azure

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


# Plan and implement data platform resources

- https://docs.microsoft.com/en-us/learn/paths/plan-implement-data-platform-resources/

## Deploy IaaS solutions with Azure SQL

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

##  Deploy PaaS solutions with Azure SQL

**Deployment models**

Azure SQL Database is available in two different deployment models:

- Single database – a single database that is billed and managed on a per database level. You manage each of your databases individually from scale and data size perspectives. Each database deployed in this model has its own dedicated resources, even if deployed to the same logical server.

- Elastic Pools – a group of databases that are managed together and share a common set of resources. Elastic pools provide a cost-effective solution for software as a service application model, since resources are shared between all databases. You can configure resources based either on the DTU-based purchasing model or the vCore-based purchasing model.

Purchase models

    DTU purchasing model is only supported by Azure SQL Database.

Serverless

    SQL Database serverless is currently only supported in the General Purpose tier in the vCore purchasing model.

Backups

    Copy-only backup to Azure blob storage is available for SQL Managed Instance. SQL Database does not support this feature.

**Active geo-replication**

Geo-replication is a business continuity feature that asynchronously replicates a database to up to four secondary replicas. As transactions are committed to the primary (and its replicas within the same region), the transactions are sent to the secondaries to be replayed. Because this communication is done asynchronously, the calling application does not have to wait for the secondary replica to commit the transaction prior to SQL Server returning control to the caller.

**Hyperscale**

Azure SQL Database has been limited to 4 TB of storage per database for many years. This restriction is due to a physical limitation of the Azure infrastructure. Azure SQL Database Hyperscale changes the paradigm and allows for databases to be 100 TB or more. Hyperscale introduces new horizontal scaling techniques to add compute nodes as the data sizes grow.

**Security considerations**

Azure SQL Database Hyperscale also supports Row-Level security. Row-Level Security enables customers to control access to rows in a database table based on the characteristics of the user executing a query (for example, group membership or execution context).


    SQL Database Hyperscale does not support the following features:

    SQL Managed Instance
    Elastic Pools
    Geo-replication
    Query Performance Insights

## Evaluate strategies for migrating to Azure SQL

There are many benefits to running on the latest release of SQL Server, including enhancements in the following categories:

- Performance
- Security
- Availability
- Query functionality

Many organizations are migrating their database platform to Azure SQL to reduce licensing costs. Migrating to Azure SQL platform is made easier by the Azure Database Migration Service (DMS). DMS supports both homogenous (for example, MySQL in a Virtual Machine to Azure SQL Database) and heterogenous sources (for example, Oracle in a Virtual Machine to Azure Database for PostgreSQL) migrations.

There are several tools available to help with the migration process. This next section looks at some of the options and methods for migration.

## Migrate SQL workloads to Azure SQL Databases

A single database has its own resources and is deployed to a logical SQL Database server where it's managed. Elastic pool databases are deployed onto a single SQL Database server where resources are shared between all databases.

**Security**

- Support for Azure Active Directory authentication
- Cloud-only security features such as Advanced Threat Protection
- Transparent Data Encryption (TDE) enabled by default
- Support for dynamic and static data masking, row-level security, and Always Encrypted
- Firewall allow list

**Migrate using the Data Migration Assistant**

You use the Data Migration Assistant to help migrate your SQL Server workload to a single or a pooled Azure SQL Database, if your organization can tolerate downtime. Here are the five steps required to do this work:

- Use the Data Migration Assistant to assess the database for compatibility issues.
- Use the compatibility report to prepare the fixes required in a Transact SQL script.
- Make a copy of the database that's transactionally consistent.
- Deploy the Transact SQL script with the fixes to the copy of the database.
- Migrate the database copy to a new Azure SQL Database by using the Data Migration Assistant.

**During migration, there are several best practices you can employ for importing the database into Azure SQL Database, including:**

- Choose the highest service tier and compute size that your budget allows to maximize the transfer performance. To save on cost, you can scale down after the migration completes.

- Minimize the distance between your BACPAC file and the destination data center.
- Disable autostatistics during migration.
- Partition tables and indexes.
- Drop indexed views and recreate them when finished.
- Remove rarely queried historical data to another database and migrate it to a separate Azure SQL Database. You can then query this historical data using elastic queries.
- After migration, update of all the statistics in the database.

If you need a database to remain available to users throughout the migration process, you can use transactional replication to move the data.

**Transactional replication considerations**

- Replicated tables must have a primary key
- Transactional replication can't be configured from the Azure portal
- Using the latest version of SQL Server management tools is recommended


**Define backup and recovery options for Azure SQL Database**

In Azure SQL Database, backups are taken automatically and kept for between 7 and 35 days. With the DTU model, a database under the Basic tier benefits from seven-day retention. Standard and Premium databases have 35 days retention. Under the vCore purchasing model, the default retention period is seven days, which can be increased up to 35 days.

Backups are stored on Azure read-access geo-redundant storage (RA-GRS) to ensure they're still available during a data center outage. To provide a point-in-time restore (PITR) capability, Azure SQL Database does transaction log backups every 5-10 minutes. There are differential backups every 12 hours. Alongside PITR, geo-restore is used to restore databases to another geographical region during a region-wide outage.

Backups are kept for longer than 35 days by using the Long-Term Retention capability. You can keep weekly, monthly, or full backups in this capability for up to 10 years in RA-GRS storage containers. This backup retention is ideal for organizations that have to meet legislative or regulatory requirements.

**Azure SQL Database provides the following business continuity capabilities:**

- Active geo-replication: provides a readable secondary replica for a given database in the same or different Azure region. Active-geo replication asynchronously replicates data by using the same technology as Always On availability groups. Up to four secondary replicas are permitted, and can be used for read-only workloads. You invoke the failover process using the application or via manual procedures with the Azure CLI, PowerShell, Transact-SQL, or the REST API.

- Auto failover groups: builds on the capabilities of active geo-replication by replicating and failing over a group of databases on an Azure SQL Database server. Grouping the databases allows multiple databases to be recovered if there's an outage.
- Geo-restore: uses geo-redundant backups to recover a database to any Azure SQL Database server, in any region. Backups are stored on geo-replicated storage, which means there's a delay between when the backup is taken, and when it's replicated to the other region.
- Zone-redundant databases: by default, replicas in the premium availability model are located in the same physical data center. Azure availability zones allow different replicas to be hosted in different zones (data centers) within the same region.

## Migrate SQL workloads to Azure Managed Instances

The goal of Azure SQL managed instance is to provide SQL Server applications with a fully managed PaaS experience in the Azure cloud. Azure SQL Database managed instance is also a fully featured SQL PaaS experience with all the critical features and capabilities of the SQL Server platform.

While Azure SQL Database is powerful, most current applications have too many technologies that exist outside the database scope. This situation leads to vendor support challenges and expensive development cycles that most organizations can't support. Azure SQL Database managed instance, code-named "Cloud Lifter", was designed to eliminate these blockers to migrating your application databases to a SQL-based PaaS solution in Azure, without having to redesign the application.

![img](/img/2-easy-migration.png)


- Security features. You can enable Advanced Data Security features at the SQL Database managed instance scope just as you do at the database level. These features include the Vulnerability Assessment and the Advance Threat Protection settings. You can also enable specific Advanced Threat Detection features and schedule periodic recurring scans that send security reports to administrators. Finally, at the managed instance level, you can configure Transparent Data Encryption (TDE) and whether you want to bring your own key (BYOK) for encryption.

- Secure network isolation. One of the unique aspects of managed instance, network security isolation is where managed instance has complete security isolation from any other tenant in the Azure cloud. In a typical default deployment SQL endpoint, managed instance is solely exposed through a private IP address that only allows connectivity from private Azure networks or hybrid networks. For on-premises applications to connect to managed instance, you'd need an Azure ExpressRoute configuration or a VPN gateway.


**Networking**

Azure SQL Database managed instance must be deployed within an Azure virtual network, with the subnet dedicated to managed instances only. SQL Database managed instance is fully isolated. The compute and storage are placed in a virtual cluster that's fully isolated from all other tenants in Azure.

Connect your on-premises resources using VPN tunneling or a route gateway to SQL Database managed instances. You can then use these instances as any others in your network. By connecting on-premises resources to SQL Database managed instance like this, you use managed instance as an extension of your on-premises datacenter.

If you have any back-end or front-end subnets in your on-premises network, you can establish VNET-to-subnet connections between them. You then use SQL connections from your web applications or link Azure SQL managed instance to your on-premises database. SQL Database managed instance becomes just an extension to your on-premises SQL solution and your organization’s on-premises network.

**Creating the Azure Database Migration Service**

The Azure Database Migration Service (DMS) is a fully managed service designed to enable seamless migrations from multiple database sources to Azure data platforms with minimal downtime. This service streamlines the tasks required to move existing third-party and SQL Server databases to Azure. DMS is a free service that supports migrations of different databases to Azure database offerings. DMS can migrate MySQL, PostgreSQL, MariaDB databases to Azure Database for MySQL/PostgreSQL/MariaDB, and also supports SQL Server migrations, including SQL MI.


**Connectivity options with on-premises servers**

Before you choose a data synchronization method, it's important to ensure you have connectivity that's secure. There are three different connectivity options available to establish communication between computers on-premises and resources in Azure.

- Point-to-Site. A Point-to-Site (P2S) VPN gateway connection lets you create a secure connection to your virtual network from an individual client computer.
 
- Site-to-Site. A Site-to-Site VPN gateway is used to connect an entire on-premises site to the Azure network.
- ExpressRoute. Azure ExpressRoute enables you to create private connections between Azure datacenters and on-premises infrastructure, or infrastructure in a colocation environment. ExpressRoute connections don't go over the public internet, and offer more reliability, faster speeds, lower latencies, and higher security than typical internet connections.

**Azure SQL Database managed instance public endpoint secure access**

To enable public endpoint for managed instance, two steps are required. For SoD, you'll need two separate roles, with the following database and network permissions, to complete these steps:

- A database administrator who has RBAC permissions in scope Microsoft.Sql/managedInstances/* must run a PowerShell script to enable public endpoint for managed instance.
- A network administrator who has RBAC permissions in scope Microsoft.Network/* must open the port 3342 used by the public endpoint on the network security group (NSG), and provide a UDR route to avoid asymmetric routing.

![img](/img/4-public-endpoint-secure-access.png)


    Although you could use backup and restore to move data from the cloud to on-premises databases, this isn't supported by Microsoft because managed instance is always at the latest version. You can't restore backups from the latest version of SQL Server to an earlier version.

**BACPAC file using SqlPackage**

A BACPAC file is simply a zipped version of your metadata and the data from your database. You can use this deployment method for Azure SQL Database, but managed instance doesn't support a migration using BACPAC in the Azure portal. Instead, you must use the SQLPackage utility, and the BACPAC file.

**Bulk Copy Program (BCP)**

BCP is a command-line tool that exports tables to files so you can import them. Use this approach to migrate from a single Azure SQL Database to Azure SQL managed instance and back.

**SQL Server Integration Service (SSIS)**

SSIS is primarily used for extract, transform, and load (ETL) tasks, but its control flow is robust enough to create a system level execution engine. The data flow is powerful enough to handle any volume of data transformation and manipulation tasks with auditing, debugging, and full source control support.

**Azure Data Factory (ADF)**

ADF is built for data movement and orchestration, with the focus on ingestion. ADF has the integration runtime support to run SSIS packages, and the public internet support for SQL Database managed instance.

**Transactional replication**

Transactional replication can copy data from your managed instance to any SQL Server. Transactional replication is a convenient approach for migrating data to and from a managed instance.

**Connecting applications to a managed instance**

An Azure SQL Database managed instance must be placed inside an Azure virtual network subnet that's dedicated to managed instances. This deployment gives you a secure private IP address and the ability to connect to on-premises networks.

![img](/img/4-public-endpoint-secure-access.png)


Managed instances depend on Azure services such as Azure Storage for backups, Azure Event Hubs for telemetry, Azure Active Directory for authentication, and Azure Key Vault for Transparent Data Encryption (TDE).

The managed instances make connections to these services.

All communications are encrypted and signed using certificates. To check the trustworthiness of communicating parties, managed instances constantly verify these certificates through certificate revocation lists. If the certificates are revoked, the managed instance closes the connections to protect the data.

# Implement a secure environment for a database service

