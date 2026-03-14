# Architecture

## Network Design
- Host-only network
- NAT network
- Subnet range 192.168.56.0/24 - 192.168.56.7/24

## Components
- Oracle VirtualBox Manager
- Linux archlinux 6.19.6-arch1-1 (Attacker - host)
- Wazuh 4.14 Server
- Windows 10 build version 10.0.19041.2673 (Target)
- Linux ubuntu 6.8.0-101-generic (Target)
- Hydra
- SSH

## Log Flow
Agents → Wazuh Manager → Indexer → Dashboard
