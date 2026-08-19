The lab is designed to practice Active Directory, DNS, users, groups, Group Policy, permissions, PowerShell administration, and troubleshooting.

## Virtual machines

### DC01

Operating System: Windows Server

Role:
- Domain controller
- Active Directory Domain Services
- DNS

### PC01

Operating System: Windows 11

Role:
- Domain-joined workstation
- Client testing

## Domain

Domain name: techlab.local

## Network

The lab uses a private virtual network in VMware.

## Architecture

DC01
│
├── Active Directory
├── DNS
└── Domain Controller
         │
         │
         ↓
       PC01
 Windows 11 Client

