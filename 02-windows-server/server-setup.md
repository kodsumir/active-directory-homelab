# Windows Server Setup

## Objective

Install and prepare Windows Server in VMware for use in the
Active Directory lab.

---

## Lab Environment

- Hypervisor: VMware
- Operating System: Windows Server
- Server Hostname: DC01
- Network: Private lab network

---

## 1. Create Windows Server VM

A Windows Server virtual machine was created in VMware.

### Steps

1. Open VMware.
2. Create a new virtual machine.
3. Select the Windows Server ISO.
4. Configure the virtual machine hardware.
5. Start the virtual machine.
6. Install Windows Server.
7. Create the local Administrator account.
8. Complete the installation.
9. Log in to Windows Server.

---

## 2. Check Windows Server Version

### Command

```powershell
winver
```

### Purpose

Displays the installed Windows version and build number.

---

## 3. Check System Information

### Command

```powershell
systeminfo
```

### Purpose

Displays detailed information about the Windows Server,
including:

- Operating system
- Hostname
- Processor
- Memory
- Windows version
- Network information

---

## 4. Configure Server Hostname

The server was given a meaningful hostname before being used
in the lab.

### Check Current Hostname

```powershell
hostname
```

### Rename the Server

Run PowerShell as Administrator:

```powershell
Rename-Computer -NewName "DC01"
```

Restart the server:

```powershell
Restart-Computer
```

### Verify

```powershell
hostname
```

Expected result:

```text
DC01
```

---

## 5. Windows Updates

Windows Server was checked for available updates.

### Location

**Settings → Windows Update**

Available updates were installed where appropriate.

### Why

Keeping Windows Server updated helps improve:

- Security
- Stability
- Reliability
- Compatibility

---

## 6. Check Date and Time

### Check Current Date and Time

```powershell
Get-Date
```

### Check Timezone

```powershell
Get-TimeZone
```

### Why

Correct time configuration is important for server
administration and authentication.

---

## 7. PowerShell

PowerShell is used to administer and troubleshoot Windows Server.

### Check PowerShell Version

```powershell
$PSVersionTable
```

### List Commands

```powershell
Get-Command
```

### Get Help

```powershell
Get-Help Get-Service
```

---

## 8. Windows Services

Windows services can be viewed and managed using PowerShell.

### List All Services

```powershell
Get-Service
```

### Check a Specific Service

```powershell
Get-Service <service-name>
```

Example:

```powershell
Get-Service WinRM
```

### Service Status

A service can have statuses such as:

```text
Running
Stopped
```

---

## 9. Configure Network

The Windows Server was connected to the VMware private
network.

### Network Information

Record the actual values used in the lab:

```text
IP Address:      192.168.88.131
Subnet Mask:     255.255.255.0
Default Gateway: 192.168.88.2
DNS Server:      ::1
                 127.0.0.1
```

### Check Network Configuration

```powershell
Get-NetIPConfiguration
```

### Check IP Addresses

```powershell
Get-NetIPAddress
```

### Check Network Adapter

```powershell
Get-NetAdapter
```

---

## 10. Test Network Connectivity

### Test Default Gateway

```powershell
ping <gateway-ip>
```

Example:

```powershell
ping 192.168.10.1
```

### Test Internet Connectivity

```powershell
ping 8.8.8.8
```

### Why

Ping can be used to determine whether the server can
communicate with another device.

---

## 11. Check DNS Settings

DNS settings can be viewed using:

```powershell
Get-DnsClientServerAddress
```

### Purpose

Displays the DNS servers configured on the network adapter.

> Detailed DNS configuration will be documented separately
> in `04-dns/dns-configuration.md`.

---

## 12. Check Windows Firewall

### Command

```powershell
Get-NetFirewallProfile
```

### Purpose

Displays the status and configuration of the Windows Firewall
profiles.

The main profiles are:

```text
Domain
Private
Public
```

---

## 13. Server Manager

Server Manager is the main graphical management tool for
Windows Server.

It can be used to:

- View server information
- Manage roles
- Manage features
- Access administrative tools
- Monitor server status

---

# Verification

The following commands were used to verify the basic
Windows Server configuration.

### Hostname

```powershell
hostname
```

### Windows Version

```powershell
winver
```

### System Information

```powershell
systeminfo
```

### Network Configuration

```powershell
Get-NetIPConfiguration
```

### Network Adapter

```powershell
Get-NetAdapter
```

### DNS Configuration

```powershell
Get-DnsClientServerAddress
```

### Windows Services

```powershell
Get-Service
```

### Firewall

```powershell
Get-NetFirewallProfile
```

---

# What I Learned

- How to create a Windows Server VM in VMware.
- How to install Windows Server.
- How to rename a Windows Server.
- How to check Windows Server information.
- How to use PowerShell for administration.
- How to check Windows services.
- How to configure and verify networking.
- How to test network connectivity.
- How to check DNS settings.
- How to check Windows Firewall status.
- How to perform basic Windows Server administration.
