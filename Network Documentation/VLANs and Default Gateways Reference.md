# VLANs and Default Gateways Reference

Source: *Connections & IPv4 Addresses.xlsx*

This document provides the IP addressing scheme for all user and management VLANs, along with their highly available HSRP default gateways.

## VLANs and HSRP Virtual IPs

| VLAN | Name | Office | Subnet | HSRP Virtual IP (Gateway) | Switch 1 SVI | Switch 2 SVI | Other Static Devices |
|---|---|---|---|---|---|---|---|
| 99 | Management | A | 10.0.0.0/28 | 10.0.0.1 | DSW-A1: 10.0.0.2 | DSW-A2: 10.0.0.3 | ASW-A1: 10.0.0.4, ASW-A2: 10.0.0.5, ASW-A3: 10.0.0.6, WLC1: 10.0.0.7 |
| 10 | PCs | A | 10.1.0.0/24 | 10.1.0.1 | DSW-A1: 10.1.0.2 | DSW-A2: 10.1.0.3 | n/a |
| 20 | Phones | A | 10.2.0.0/24 | 10.2.0.1 | DSW-A1: 10.2.0.2 | DSW-A2: 10.2.0.3 | n/a |
| 40 | Wi-Fi | A | 10.6.0.0/24 | 10.6.0.1 | DSW-A1: 10.6.0.2 | DSW-A2: 10.6.0.3 | n/a |
| 99 | Management | B | 10.0.0.16/28 | 10.0.0.17 | DSW-B1: 10.0.0.18 | DSW-B2: 10.0.0.19 | ASW-B1: 10.0.0.20, ASW-B2: 10.0.0.21, ASW-B3: 10.0.0.22 |
| 10 | PCs | B | 10.3.0.0/24 | 10.3.0.1 | DSW-B1: 10.3.0.2 | DSW-B2: 10.3.0.3 | n/a |
| 20 | Phones | B | 10.4.0.0/24 | 10.4.0.1 | DSW-B1: 10.4.0.2 | DSW-B2: 10.4.0.3 | n/a |
| 30 | Servers | B | 10.5.0.0/24 | 10.5.0.1 | DSW-B1: 10.5.0.2 | DSW-B2: 10.5.0.3 | n/a |
