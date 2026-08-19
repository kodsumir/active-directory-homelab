# Active Directory Lab

A hands-on Windows Server and Active Directory homelab designed to
practice real-world system administration tasks.

## Project Overview

This project simulates a small company IT environment using
Windows Server and Windows 11 virtual machines.

The goal is to build and manage a Windows domain environment
and practice common system administration tasks.

## Objectives

- Deploy Windows Server in VMware
- Configure a Domain Controller
- Install Active Directory Domain Services (AD DS)
- Configure DNS
- Create and manage users
- Create and manage security groups
- Create Organizational Units (OUs)
- Join Windows clients to the domain
- Configure Group Policy
- Configure file shares and permissions
- Practice PowerShell administration
- Practice Windows Server troubleshooting

## Lab Environment

### Virtualization

- VMware

### Server

- Windows Server
- Hostname: DC01
- Role: Domain Controller

### Client

- Windows 11
- Hostname: PC01
- Role: Domain-joined workstation

### Domain

`techlab.local`

## Network

The lab uses a private virtual network created in VMware.

Example:

```text
Network: 192.168.10.0/24

DC01:
IP: 192.168.10.10

PC01:
DHCP

Gateway:
192.168.10.1
```

> The IP addresses shown above are examples and will be replaced
> with the actual addresses used in the lab.

## Architecture

```text
                    TECHLAB.LOCAL
                         │
                        DC01
                  Windows Server
                         │
          ┌──────────────┼──────────────┐
          │              │              │
   Active Directory     DNS       Group Policy
          │
          │
         PC01
     Windows 11
   Domain Client
```

## Active Directory Structure

```text
TECHLAB.LOCAL
│
├── Users
├── Groups
├── Computers
└── Servers
```

This structure will be expanded as the lab progresses.

## Project Structure

- `01-lab-design/`
- `02-windows-server/`
- `03-active-directory/`
- `04-dns/`
- `05-users-and-groups/`
- `06-organizational-units/`
- `07-domain-join/`
- `08-group-policy/`
- `09-file-shares/`
- `10-powershell/`
- `11-security/`
- `12-troubleshooting/`
- `13-final-project/`

## Skills Practiced

### Windows Server

- Server installation
- Server configuration
- Windows services
- Server administration

### Active Directory

- Domain Controller deployment
- User management
- Group management
- Organizational Units
- Domain management
- Computer management

### Networking

- IPv4 addressing
- DNS
- DHCP
- Domain name resolution
- Network troubleshooting

### Group Policy

- Creating Group Policy Objects
- Applying policies to users and computers
- Basic security policies

### File Services

- File shares
- NTFS permissions
- Share permissions
- Access control

### PowerShell

- Active Directory administration
- User management
- Group management
- Computer management
- Basic automation

### Troubleshooting

- DNS troubleshooting
- Domain join troubleshooting
- Network troubleshooting
- Authentication troubleshooting
- Windows service troubleshooting

## Progress

- [ ] Lab design
- [ ] Windows Server installation
- [ ] Windows 11 installation
- [ ] Network configuration
- [ ] Active Directory Domain Services
- [ ] Domain Controller
- [ ] DNS
- [ ] Users
- [ ] Groups
- [ ] Organizational Units
- [ ] Domain join
- [ ] Group Policy
- [ ] File shares
- [ ] Permissions
- [ ] PowerShell
- [ ] Security
- [ ] Troubleshooting
- [ ] Final project

## Related Projects

The virtual machines used in this project were created using my
separate VMware and operating system setup project.

- [VM Lab Setup](YOUR-VM-LAB-REPOSITORY-LINK)

## Disclaimer
This is a personal homelab created for learning and practicing
system administration concepts.
This is a personal homelab created for learning and practicing
system administration concepts.
