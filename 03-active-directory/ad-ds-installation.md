# Active Directory Domain Services Installation

## Objective

Deploy Windows Server as the first Domain Controller
for the TechLab Active Directory environment.

## Server

Hostname: DC01

Operating System: Windows Server

## Domain

techlab.local

NetBIOS name: TECHLAB

## AD DS Installation

Active Directory Domain Services was installed using:

Server Manager → Add Roles and Features

The server was then promoted to a Domain Controller.

## Deployment Configuration

A new forest was created.

Root domain:

techlab.local

## Domain Controller Options

DNS Server: Enabled

Global Catalog: Enabled

Read-only Domain Controller: Disabled

Directory Services Restore Mode (DSRM):
Configured and stored securely outside this repository.

## DNS

DNS was installed as part of the Domain Controller deployment.

DNS delegation was not configured because this is an
isolated lab environment and this server is the first
DNS server for the lab domain.

## NetBIOS

TECHLAB

## Active Directory Database

Default database path:

C:\Windows\NTDS

## SYSVOL

Default SYSVOL path:

C:\Windows\SYSVOL

## Verification

### Check hostname
```powershell
hostname

```powershell
hostname

**Purpose:**  
Displays information about the current Active Directory domain.

**What to check:**

```text
DNSRoot       : techlab.local
NetBIOSName   : TECHLAB
```

---

### 2. Check DNS Service

```powershell
Get-Service DNS
```

**Purpose:**  
Checks whether the Windows DNS Server service is running.

**Expected status:**

```text
Running
```

---

### 3. Check Active Directory Domain Services

```powershell
Get-Service NTDS
```

**Purpose:**  
Checks whether the Active Directory Domain Services service is running.

**Expected status:**

```text
Running
```

---

### 4. Check Netlogon Service

```powershell
Get-Service Netlogon
```

**Purpose:**  
Checks whether the Netlogon service is running.

Netlogon is used for domain authentication and communication
between domain-joined computers and the Domain Controller.

**Expected status:**

```text
Running
```

---

### 5. Test DNS Resolution

```powershell
nslookup techlab.local
```

**Purpose:**  
Tests whether the `techlab.local` domain can be resolved through DNS.

**Expected result:**  
The DNS server should respond with information about the
`techlab.local` domain.

---

### 6. Test Domain Controller DNS Resolution

```powershell
nslookup DC01.techlab.local
```

**Purpose:**  
Tests whether the Domain Controller hostname can be resolved
through DNS.

**Expected result:**  
The hostname should resolve to the IP address of the Domain Controller.

---

### 7. Run Domain Controller Diagnostics

```powershell
dcdiag
```

**Purpose:**  
Runs diagnostic tests against the Domain Controller.

It can help identify problems with:

- Active Directory
- DNS
- Domain Controller services
- Connectivity
- Replication
- Domain configuration

**Expected result:**  
The Domain Controller diagnostic tests should complete without
critical errors.

---

## Verification Summary

The following checks were performed after Domain Controller
promotion:

| Check | Command | Purpose |
|---|---|---|
| Active Directory domain | `Get-ADDomain` | Verify the AD domain |
| DNS service | `Get-Service DNS` | Check DNS service status |
| AD DS service | `Get-Service NTDS` | Check AD DS service status |
| Netlogon | `Get-Service Netlogon` | Check domain authentication service |
| Domain DNS | `nslookup techlab.local` | Test DNS resolution |
| DC DNS | `nslookup DC01.techlab.local` | Resolve the Domain Controller |
| DC health | `dcdiag` | Diagnose Domain Controller |

## What I Learned

- `Get-ADDomain` displays Active Directory domain information.
- `Get-Service DNS` checks the Windows DNS service.
- `Get-Service NTDS` checks the Active Directory Domain Services service.
- `Get-Service Netlogon` checks the Netlogon service.
- `nslookup` can be used to test DNS resolution.
- `dcdiag` can be used to diagnose Domain Controller health.
- DNS is an important part of an Active Directory environment.
