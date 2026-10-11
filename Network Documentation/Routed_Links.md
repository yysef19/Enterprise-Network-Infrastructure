# Routed Links and Backbone Addressing

Source: *Connections & IPv4 Addresses.xlsx*

This document outlines the point-to-point /30 routed links forming the OSPF Area 0 backbone, external internet links, and device loopback interfaces.

## 1. Point-to-Point Routed Links (/30)

| Link | Subnet | Side A | Side B |
|---|---|---|---|
| R1 ↔ ISPA | 203.0.113.0/30 | R1 G0/0/0: 203.0.113.2 | ISPA: 203.0.113.1 |
| R1 ↔ ISPB | 203.0.113.4/30 | R1 G0/1/0: 203.0.113.6 | ISPB: 203.0.113.5 |
| R1 ↔ CSW1 | 10.0.0.32/30 | R1 G0/0: 10.0.0.33 | CSW1 G1/0/1: 10.0.0.34 |
| R1 ↔ CSW2 | 10.0.0.36/30 | R1 G0/1: 10.0.0.37 | CSW2 G1/0/1: 10.0.0.38 |
| CSW1 ↔ CSW2 | 10.0.0.40/30 | CSW1 Po1: 10.0.0.41 | CSW2 Po1: 10.0.0.42 |
| CSW1 ↔ DSW-A1 | 10.0.0.44/30 | CSW1 G1/1/1: 10.0.0.45 | DSW-A1 G1/1/1: 10.0.0.46 |
| CSW1 ↔ DSW-A2 | 10.0.0.48/30 | CSW1 G1/1/2: 10.0.0.49 | DSW-A2 G1/1/1: 10.0.0.50 |
| CSW1 ↔ DSW-B1 | 10.0.0.52/30 | CSW1 G1/1/3: 10.0.0.53 | DSW-B1 G1/1/1: 10.0.0.54 |
| CSW1 ↔ DSW-B2 | 10.0.0.56/30 | CSW1 G1/1/4: 10.0.0.57 | DSW-B2 G1/1/1: 10.0.0.58 |
| CSW2 ↔ DSW-A1 | 10.0.0.60/30 | CSW2 G1/1/1: 10.0.0.61 | DSW-A1 G1/1/2: 10.0.0.62 |
| CSW2 ↔ DSW-A2 | 10.0.0.64/30 | CSW2 G1/1/2: 10.0.0.65 | DSW-A2 G1/1/2: 10.0.0.66 |
| CSW2 ↔ DSW-B1 | 10.0.0.68/30 | CSW2 G1/1/3: 10.0.0.69 | DSW-B1 G1/1/2: 10.0.0.70 |
| CSW2 ↔ DSW-B2 | 10.0.0.72/30 | CSW2 G1/1/4: 10.0.0.73 | DSW-B2 G1/1/2: 10.0.0.74 |

## 2. Loopback Interfaces (/32)

| Device | Interface | IP Address |
|---|---|---|
| R1 | Loopback0 | 10.0.0.76/32 |
| CSW1 | Loopback0 | 10.0.0.77/32 |
| CSW2 | Loopback0 | 10.0.0.78/32 |
| DSW-A1 | Loopback0 | 10.0.0.79/32 |
| DSW-A2 | Loopback0 | 10.0.0.80/32 |
| DSW-B1 | Loopback0 | 10.0.0.81/32 |
| DSW-B2 | Loopback0 | 10.0.0.82/32 |
