
<!-- TOC -->

- [Exam DP-300: Administering Relational Databases on Microsoft Azure](#exam-dp-300-administering-relational-databases-on-microsoft-azure)
- [Introduction to Azure database administration](#introduction-to-azure-database-administration)
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

- [Troubleshoot transient connection errors in SQL Database and SQL Managed Instance](https://docs.microsoft.com/en-us/azure/azure-sql/database/troubleshoot-common-connectivity-issues?view=azuresql)

- [Automated backups - Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/automated-backups-overview?tabs=single-database&view=azuresql)
- [Tutorial: Set up SQL Data Sync between databases in Azure SQL Database and SQL Server](https://docs.microsoft.com/en-us/azure/azure-sql/database/sql-data-sync-sql-server-configure?view=azuresql)
- [Features of SQL Database and SQL Managed Instance](https://docs.microsoft.com/en-us/azure/azure-sql/database/features-comparison?view=azuresql)
- [License Mobility through Software Assurance on Azure](https://azure.microsoft.com/pl-pl/pricing/license-mobility/)
- [Automated backups - Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/automated-backups-overview?view=azuresql)
- [PREDICT (Transact-SQL)](https://docs.microsoft.com/en-us/sql/t-sql/queries/predict-transact-sql?view=sql-server-ver16)


# Plan and implement data platform resources

## Deploy IaaS solutions with Azure SQL

- [General purpose ](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-general)

- [Compute optimized](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-compute)
- [Memory optimized](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-memory)
- [Storage optimized](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-storage)
- [GPU](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-gpu)
- [High performance compute](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-hpc)
- [Best practices for SQL Server on Azure VMs](https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/performance-guidelines-best-practices-checklist?view=azuresql)
- [Provision SQL Server on Azure VM (Azure portal)](https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/create-sql-vm-portal?view=azuresql)
- [Business continuity and HADR for SQL Server on Azure Virtual Machine](https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/business-continuity-high-availability-disaster-recovery-hadr-overview?view=azuresql#hybrid-it-disaster-recovery-solutions)
- [Understanding Azure storage redundancy offerings](https://techcommunity.microsoft.com/t5/azure-storage-blog/understanding-azure-storage-redundancy-offerings/ba-p/1431700)
- [Azure Arc overview](https://docs.microsoft.com/en-us/azure/azure-arc/overview)
- [Create a site-to-site VPN connection in the Azure portal](https://docs.microsoft.com/en-us/azure/vpn-gateway/tutorial-site-to-site-portal)
- [What is Azure ExpressRoute?](https://docs.microsoft.com/en-us/azure/expressroute/expressroute-introduction)
- [Checklist: Best practices for SQL Server on Azure VMs](https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/performance-guidelines-best-practices-checklist?view=azuresql)

## Deploy PaaS solutions with Azure SQL

- [DTU-based purchasing model overview](https://docs.microsoft.com/en-us/azure/azure-sql/database/service-tiers-dtu?view=azuresql)

- [Automated backups - Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/automated-backups-overview?view=azuresql)
- [Prepare your environment for a link - Azure SQL Managed Instance](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/managed-instance-link-preparation?view=azuresql)
- [Deploy Azure SQL Managed Instance to an instance pool](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/instance-pools-configure?view=azuresql&tabs=powershell)
- [What's new in Azure SQL Managed Instance?](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/doc-changes-updates-release-notes-whats-new?view=azuresql)
- [Azure SQL Edge ](https://azuremarketplace.microsoft.com/pl-PL/marketplace/apps/microsoftsqledge.azure-sql-edge?tab=overview)
- [Securing Azure SQL Edge](https://docs.microsoft.com/en-us/azure/azure-sql-edge/security-overview)
- [Tutorial: Sync data from SQL Edge to Azure SQL Database by using SQL Data Sync](https://docs.microsoft.com/en-us/azure/azure-sql-edge/tutorial-sync-data-sync)
- [Azure IoT Edge supported systems](https://docs.microsoft.com/en-us/azure/iot-edge/support?view=iotedge-2020-11)
- [Connect and query Azure SQL Edge](https://docs.microsoft.com/en-us/azure/azure-sql-edge/connect)

## Evaluate strategies for migrating to Azure SQL

- [ALTER DATABASE (Transact-SQL) compatibility level](https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql-compatibility-level?view=sql-server-ver16)

- [Pricing calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
- [Migration and other tools](https://docs.microsoft.com/en-us/sql/tools/overview-sql-tools?view=sql-server-ver16#migration-and-other-tools)

## Migrate SQL workloads to Azure SQL Databases

- [Retry guidance for Azure services](https://docs.microsoft.com/en-us/azure/architecture/best-practices/retry-service-specific)
- [Azure Database Migration Guides](https://docs.microsoft.com/en-us/data-migration/?step=1)
- [Transactional replication with Azure SQL Managed Instance (Preview)](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/replication-transactional-overview?view=azuresql)

## Migrate SQL workloads to Azure Managed Instances

- [What is Azure SQL Managed Instance?](https://docs.microsoft.com/en-us/azure/azure-sql/managed-instance/sql-managed-instance-paas-overview?view=azuresql)

- [Tutorial: Migrate SQL Server to an Azure SQL Managed Instance online using DMS](https://docs.microsoft.com/en-us/azure/dms/tutorial-sql-server-managed-instance-online)
- [Tutorial: Migrate SQL Server to an Azure SQL Managed Instance offline using DMS](https://docs.microsoft.com/en-us/azure/dms/tutorial-sql-server-to-managed-instance?toc=%2Fazure%2Fsql-database%2Ftoc.json)
- [Differences between compatibility level 140 and level 150](https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql-compatibility-level?view=sql-server-2017#differences-between-compatibility-level-140-and-level-150)
- [Pvk2Pfx](https://docs.microsoft.com/en-us/windows-hardware/drivers/devtest/pvk2pfx)

# Implement a secure environment for a database service