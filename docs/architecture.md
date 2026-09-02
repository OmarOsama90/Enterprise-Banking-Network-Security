# Architecture

## Logical Design

The lab is organized as a three-site enterprise banking network:

**Egypt HQ (hub) → Simulated ISP/WAN → Libya Branch / Tunisia Branch (spokes)**

HQ provides the central connectivity point and hosts the LDAP / Active Directory server. Remote branches establish IPsec tunnels back to HQ.

## HQ High Availability

Two FortiGate VM64-KVM devices operate as an Active-Passive cluster using FortiGate Clustering Protocol (FGCP).

- Cluster name: `HQ-Cluster`
- Primary priority: `200`
- Secondary priority: `128`
- Heartbeat: `port4`, `port5`
- Monitored links: `port1`, `port2`

The design removes a single-firewall dependency at the HQ edge.

## Identity and Access

The environment uses centralized LDAP / Active Directory authentication.

- Server: `172.30.20.111`
- Port: `389`
- Base DN: `DC=tshoot,DC=com`
- User identifier: `sAMAccountName`

Access is mapped to groups such as `Bank_Employees`, `IT_Employees`, and `SSO_Guest_Users`.

## Site-to-Site Connectivity

HQ is the IPsec hub. Libya and Tunisia are spokes.

- Libya WAN endpoint: `192.168.122.207`
- Tunisia WAN endpoint: `192.168.122.66`

The project report records successful tunnel establishment and site-to-site traffic tests.

## SD-WAN

Branch WAN links are monitored through a Performance SLA (`Check_HQ`). The lab measures latency, jitter, and packet loss to detect degraded paths.

## Addressing Plan

- HQ LAN: `172.30.20.0/24`
- Libya: `172.30.21.0/24`
- Tunisia: `172.30.22.0/24`
- Simulated WAN: `192.168.122.0/24`
- HQ management: `192.168.10.88` / `192.168.10.89`

See the full report and sanitized configuration exports for implementation-level details.
