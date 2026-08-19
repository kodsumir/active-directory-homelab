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
