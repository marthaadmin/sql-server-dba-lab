
# Backup and Restore – Practical DBA Notes (Lab Guide)

## 🧱 Overview

This document summarizes everything practiced in Backup and Restore using SQL Server. It covers:

* Manual backups
* Restore operations
* Recovery models
* SQL Server Agent jobs
* Ola Hallengren maintenance setup

---

## 🧠 1. Types of Backups

### 🔹 Full Backup

* Contains entire database
* Starting point for any restore

```sql
BACKUP DATABASE MyFirstDB
TO DISK = 'D:\Backup\MyFirstDB_Full.bak'
WITH INIT, STATS = 10;
```

---

### 🔹 Differential Backup

* Contains changes since last full backup
* Faster and smaller than full

---

### 🔹 Transaction Log Backup

* Contains all transactions since last log backup
* Required for point-in-time recovery and log shipping

```sql
BACKUP LOG MyFirstDB
TO DISK = 'D:\Backup\MyFirstDB_Log.trn';
```

---

## 🧠 2. Recovery Models

### 🔹 FULL Recovery Model

* Supports:

  * Log backups
  * Point-in-time restore
  * Log shipping

```sql
ALTER DATABASE MyFirstDB SET RECOVERY FULL;
```

---

## 🧠 3. Restore Basics

### 🔹 Simple Restore

```sql
RESTORE DATABASE MyFirstDB
FROM DISK = 'D:\Backup\MyFirstDB_Full.bak';
```

---

## 🧠 4. Common Restore Issues

### ❌ Path does not exist

* Fix: Create folder manually

### ❌ Permission denied

* Fix: Grant access to:

  * NT SERVICE\MSSQLSERVER
  * NT SERVICE\SQLSERVERAGENT

### ❌ Syntax errors

* Example: extra space inside quotes

---

## 🧠 5. SQL Server Agent Jobs

### 🔹 Purpose

Automates backup tasks

---

### 🔹 Example Job Step

```sql
BACKUP DATABASE MyFirstDB
TO DISK = 'D:\Backup\MyFirstDB_Full.bak'
WITH INIT, STATS = 10;
```

---

### 🔹 Monitoring Jobs

* Job Activity Monitor
* Job History
* Backup folder verification

---

## 🧠 6. Ola Hallengren Maintenance Solution

### 🔹 What it provides

* Automated backup framework
* Best practices built-in
* Compression, cleanup, logging

---

### 🔹 Installation

* Run `MaintenanceSolution.sql` in master database
* Creates jobs automatically

---

### 🔹 Key Jobs Created

* DatabaseBackup - USER_DATABASES - FULL
* DatabaseBackup - USER_DATABASES - DIFF
* DatabaseBackup - USER_DATABASES - LOG

---

### 🔹 Example Ola Backup Command

```sql
EXEC dbo.DatabaseBackup
@Databases = 'MyFirstDB',
@Directory = 'D:\Backup',
@BackupType = 'FULL',
@Compress = 'Y';
```

---

## 🧠 7. Job Customization (Important)

### FULL Backup Job

* Runs daily (e.g., 2 AM)

### LOG Backup Job

* Runs every 15 minutes

---

### Recommended Settings

* Compression = ON
* CleanupTime = 72 hours
* Dedicated backup folder

---

## 🧠 8. Real DBA Takeaways

* Backup location ≠ restore location
* Jobs run under service accounts (not your login)
* Always test backups and restores
* Never rely on a single backup file


