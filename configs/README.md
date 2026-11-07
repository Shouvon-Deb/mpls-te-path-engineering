# 🌐 Router Configurations

<p align="center">
  <img src="../assets/network-banner.jpg" width="100%" alt="Digital Network Infrastructure">
</p>

<h1 align="center">MPLS-TE | Router Configuration Repository</h1>

<p align="center">
  <b>Centralized Cisco IOS configurations for the MPLS Traffic Engineering lab.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-GNS3-blue?style=for-the-badge&logo=gnometerminal" />
  <img src="https://img.shields.io/badge/Vendor-Cisco-049fd9?style=for-the-badge&logo=cisco" />
  <img src="https://img.shields.io/badge/Protocol-MPLS--TE-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Routing-OSPF-green?style=for-the-badge" />
</p>

---

## 📡 Overview

This directory contains the **running configuration files** for all six Cisco 7200 routers deployed in the MPLS Traffic Engineering topology.

Each configuration represents an individual router within the lab and contains the settings used to establish the MPLS network, routing infrastructure, and traffic-engineered paths.

## 🖥️ Router Configuration Files

| Router | Configuration File |
|:---:|---|
| 🔵 R1 | [R1-running-config.txt](./R1-running-config.txt) |
| 🔵 R2 | [R2-running-config.txt](./R2-running-config.txt) |
| 🔵 R3 | [R3-running-config.txt](./R3-running-config.txt) |
| 🔵 R4 | [R4-running-config.txt](./R4-running-config.txt) |
| 🔵 R5 | [R5-running-config.txt](./R5-running-config.txt) |
| 🔵 R6 | [R6-running-config.txt](./R6-running-config.txt) |

## 🛠️ Network Technologies

The router configurations support the following technologies:

- **OSPF** – Interior Gateway Protocol.
- **MPLS** – Multiprotocol Label Switching.
- **MPLS-TE** – Traffic Engineering extensions.
- **RSVP-TE** – Resource Reservation Protocol for TE.
- **Explicit Routing** – Controlled traffic forwarding paths.
- **TE Tunnels** – Traffic-engineered label-switched paths.

## 🛣️ Traffic Engineering Architecture

The topology implements two explicitly defined paths between R1 and R6.

**PATH_A – Upper Route**

```text
R1 ── R2 ── R4 ── R6
```

**PATH_B – Lower Route**

```text
R1 ── R3 ── R5 ── R6
```

These paths demonstrate alternative forwarding routes through the MPLS core.

## ⚙️ Configuration Usage

1. Open the desired router configuration file.
2. Review the existing configuration.
3. Open the corresponding router console in GNS3.
4. Apply the configuration as appropriate for the lab.
5. Verify routing, MPLS forwarding, and TE tunnel operation.

> [!IMPORTANT]
> These configuration files are intended for the accompanying GNS3 topology. Interface mappings, IP addressing, and router connectivity should match the project before applying configurations.

## 🔍 Verification

The following Cisco IOS commands can be used to inspect the network:

| Command | Purpose |
|---|---|
| `show running-config` | Display active configuration |
| `show ip route` | Inspect routing table |
| `show ip ospf neighbor` | Check OSPF adjacencies |
| `show mpls interfaces` | Inspect MPLS-enabled interfaces |
| `show mpls ldp neighbor` | Inspect LDP neighbors, if configured |
| `show mpls traffic-eng tunnels` | Inspect TE tunnels |

## 📁 Repository Structure

```text
configs/
├── README.md
├── R1-running-config.txt
├── R2-running-config.txt
├── R3-running-config.txt
├── R4-running-config.txt
├── R5-running-config.txt
└── R6-running-config.txt
```

---

<p align="center">
  <b>🚀 MPLS Traffic Engineering Lab</b>
  <br>
  <sub>Network Engineering | Cisco IOS | GNS3</sub>
</p>
