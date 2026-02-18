| Setting              | Value                          |
| -------------------- | ------------------------------ |
| Hypervisor           | VMware Workstation 17.5        |
| Operating System     | Windows Server 2016 Datacenter |
| RAM Allocated        | 4 GB                           |
| CPU                  | 2 vCPU                         |
| Disk 1 (Data – SCSI) | 30 GB                          |
| Disk 2 (OS – NVMe)   | 50 GB                          |
| Network Type         | NAT                            |
| Server Name          | SQL01                          |

Storage Layout Design

This lab uses two virtual disks to simulate production-style separation:

50 GB Disk (NVMe) → Operating System

30 GB Disk (SCSI) → SQL Server Data and Log files

Separating SQL data/log files from the operating system disk helps:

Improve performance

Reduce disk contention

Simplify backup and recovery

Follow production best practices

Screenshots
VMware Configuration

Windows Version

Server Name

IP Configuration
