# Network Plan

## Objective

Design and document the private network used by the
Active Directory lab.

## Lab Machines

| Hostname | Operating System | IP Address | Role |
|---|---|---|---|
| DC01 | Windows Server | `[DC01-IP]` | Domain Controller + DNS |
| WIN11 | Windows 11 | `[WIN11-IP]` | Domain Client |

## Network

```text
Network: [YOUR NETWORK]
Subnet Mask: [YOUR SUBNET MASK]
Default Gateway: [YOUR GATEWAY]
```

## Network Diagram

```text
              VMware
                 │
         Private Lab Network
                 │
          ┌──────┴──────┐
          │             │
        DC01           WIN11
   Windows Server    Windows 11
   Domain Controller    Client
          │
          ├── Active Directory
          └── DNS
```

## Connectivity

DC01 and WIN11 are connected to the same VMware
private network.

Connectivity was tested using:

```powershell
ping <IP-address>
```

## DNS

DC01 will provide DNS for the Active Directory domain:

```text
techlab.local
```

WIN11 will use DC01 as its DNS server when it is
configured to join the domain.

## What I Learned

- IP addresses identify devices on a network.
- Devices on the same subnet can communicate directly.
- The Domain Controller needs a predictable IP address.
- The Windows client needs network connectivity to the Domain Controller.
- Active Directory relies heavily on DNS.
