# Advanced-Windows-Server-Farm-Network

## Overview
This repository is my university project about demonstrating the implementation of WIndows Server Services to support a smart farming (E-Agriculture) system.

The services that will be configured are:
- DHCP
- DNS
- ADDS
- GPO
- NFS
- DHCP Failover
- FSRM
- DFS

---

## System Concept
This project's infrastructure is designed to:
- Support IoT-based farming devices
- Provide centralized user management
- Ensure continuous service availability
- Improve data storage and sharing

---

## Key Configuration

### DHCP Server
The DHCP server is configured to automatically assign IP addresses to client devices.

**Steps performed:**
- Configure IP address pool
- Verify client IP using ```ipconfig```
- Checke address leases in DHCP Manager

**Testing:**
- Client successfully recieved IP address
- Client can ping the server

### DNS Server
DNS is used to translate domain names into addresses.

**Steps performed:**
- Create Forward Lookup Zone
- Create Reverse Lookup Zone
- Configure DNS records

**Testing:**
- Client successfully resolves server using domain name

### Active Directory Domain Server (ADDS)
ADDS is used for centralized authentication and user management.

**Steps performed:**
- Create Organizational Units:
  - Farmer
  - Operator
- Add users to each Organizational Units
- Configured domain environment

**Testing:**
- Users successfully log in form client PC

### Group Policy Object
GPO is used to enforce security policies on client machines.

**Policies applied:**
- Disable Control Panel access
- Block Command Prompt (CMD)
- Remove Run menu

**Result:**
- Restrictions successfully applient on client systems

### NFS Server
NFS is used for file sharing between systems.

**Steps preformed:**
- Configure share directory
- Mounted NFS path on client

**Testing:**
- Client successfully accessed shared files

### Join Forest (Backup Server)
A backup server is added to the domain for redundancy.

**Steps performed:**
- Assigned static IP
- Joined existing domain
- Verify connection in Server Manager

### DHCP Failover
Failover ensures DHCP service remains available if the main server fails.

**Steps performed:**
- Configure failover relationship
- Linked main server and backup server

**Testing:**
- Main server turned off
- Backup server successfully handled DHCP requests

### File Server Resource Manager (FSRM)
FSRM is used to manage storage and control file usage.

**Steps performed:**
- Create new partition
- Configure quota limits
- Applied file screening

**Result:**
- Storage usage controlled
- File restrictions enforced

### Distributed File System (DFS)
DFS provides file replication and redundancy.

**Steps performed:**
- Create DFS Namespace
- Added folders from main and backup servers
- Configure replication

**Testing:**
- File changes replicated between servers successfully

---

## Testing Summary
| Features | Result |
|----------|--------|
| DHCP | Working |
| DNS | Working | 
| ADDS Login | Working |
| GPO | Applied |
| NFS | Working |
| Failover | Working |
| FSRM | Working |
| DFS | Working |

---

## Key Takeaways
- Leaned how to configure multiple Windows Server roles
- Implemented high availability using failover and DFS
- Applied security policies using GPO
- Built a structured network for real-world use case (E-Agriculture)

---

## Documentations

Full project documentation: [E-Agriculture's Window Server](./ImplementingAdvancedWindowsServeronE-Agriculture.pdf)
