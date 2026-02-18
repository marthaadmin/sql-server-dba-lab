SQL Server 2016 Installation
Objective

Install SQL Server 2016 (Evaluation Edition) on Windows Server 2016 using best practice configuration for a DBA lab environment.

Installation Steps
1️⃣ Launch Installation Center
2️⃣ New Stand-Alone Installation

Selected:

Installation → New SQL Server stand-alone installation

Evaluation edition selected.

3️⃣ Feature Selection

Selected:

Database Engine Services

SQL Server Replication

Client Tools Connectivity

Client Tools SDK

4️⃣ Instance Configuration

Installed as:

Default Instance
Instance ID: MSSQLSERVER

5️⃣ Server Configuration

Configured services:

SQL Server Agent → Automatic

SQL Server Database Engine → Automatic

Instant File Initialization enabled

6️⃣ Database Engine Configuration

Configured:

Mixed Mode Authentication

Strong SA password set

Windows Administrator added as SQL admin

7️⃣ Installation Complete

Installation completed successfully with product updates applied.

Outcome

SQL Server 2016 successfully installed as the default instance on server SQL01.

## Installation Screenshots

### 1️⃣ Installation Center
![Installation Center](../Screenshots/06-installation-center.png)

---

### 2️⃣ New Stand-Alone Installation (Evaluation Edition)
![New Standalone Install](../Screenshots/07-new-standalone-install.png)

---

### 3️⃣ Feature Selection
![Feature Selection](../Screenshots/08-feature-selection.png)

---

### 4️⃣ Default Instance Configuration
![Default Instance](../Screenshots/09-default-instance.png)

---

### 5️⃣ Server Configuration
![Server Configuration](../Screenshots/10-server-configuration.png)

---

### 6️⃣ Mixed Mode Configuration
![Mixed Mode](../Screenshots/11-mixed-mode-config.png)

---

### 7️⃣ Data Directories Configuration
![Data Directories](../Screenshots/13-data-directories-config.png)

---

### 8️⃣ TempDB Configuration
![TempDB Configuration](../Screenshots/14-tempdb-configuration.png)

---

### 9️⃣ Installation Completed Successfully
![Installation Complete](../Screenshots/12-installation-complete.png)



