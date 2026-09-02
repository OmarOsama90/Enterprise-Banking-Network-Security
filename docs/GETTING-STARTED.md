# Getting Started

## Purpose

This repository documents a GNS3-based enterprise banking network security lab. It is designed to be read as a portfolio project and used as a reference for rebuilding the lab in a controlled environment.

## Prerequisites

- GNS3
- FortiGate VM64-KVM images compatible with the lab
- A virtual machine/server capable of running the required GNS3 nodes
- Basic familiarity with FortiGate administration, routing, IPsec VPN, LDAP, and SD-WAN

## Rebuilding the Lab

1. Recreate the three-site topology shown in `docs/topology/topology.jpeg`.
2. Configure the addressing plan documented in `README.md` and `docs/architecture.md`.
3. Build the HQ Active-Passive HA pair and configure the heartbeat and monitored interfaces.
4. Configure the LDAP / Active Directory server and the required user groups.
5. Configure the HQ hub and Libya/Tunisia spoke IPsec relationships.
6. Configure SD-WAN link monitoring and the `Check_HQ` Performance SLA.
7. Apply environment-specific secrets manually.
8. Run the validation checks documented in `docs/testing/testing-and-results.md`.

## Configuration Exports

The files under `configs/fortigate/` are intentionally sanitized public references. They are **not complete production-ready imports**, because sensitive credentials and cryptographic material have been removed.

Use them to understand the original implementation and reproduce the configuration safely in your own isolated lab.

## Project Report

The complete academic report is available at `docs/project-report.pdf`.
