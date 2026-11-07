# 🚀 GNS3 – MPLS Traffic Engineering Lab

A portable **GNS3 network simulation project** designed to build, configure, and test **MPLS Traffic Engineering (MPLS-TE)** using OSPF, RSVP-TE, and explicit traffic-engineered paths.

## 📌 Project Overview

This project demonstrates how MPLS Traffic Engineering can be used to control packet forwarding across a network using explicitly defined paths and TE tunnels.

**Project File:** `mpls-te-path-engineering.gns3project`

## 🖧 Network Architecture

The lab consists of the following network components:

| Component | Quantity | Description |
|---|---:|---|
| Cisco 7200 Routers | 6 | Core MPLS network |
| VPCS Hosts | 2 | End-to-end connectivity testing |
| OSPF | — | Interior Gateway Protocol |
| MPLS | — | Label-based packet forwarding |
| MPLS-TE | — | Traffic Engineering |
| RSVP-TE | — | TE tunnel signaling |
| Explicit Paths | 2 | Manually defined TE routes |
| TE Tunnels | 2 | Traffic-engineered tunnels |

## 🛣️ Traffic Engineering Paths

The lab implements two explicitly defined paths between the ingress router (R1) and egress router (R6).

### PATH_A – Upper Route

```text```
R1 ── R2 ── R4 ── R6
PATH_B – Lower Route

```text```
R1 ── R3 ── R5 ── R6
Both paths provide alternative routes through the MPLS core, allowing the behavior of explicit-path traffic engineering to be explored and tested.

⚙️ Technologies
GNS3 – Network emulation platform

Cisco IOS (7200) – Router operating system

OSPF – IGP routing protocol

MPLS – Multiprotocol Label Switching

MPLS-TE – Traffic Engineering extensions

RSVP-TE – Resource Reservation Protocol for TE

Explicit Routing – Manually controlled traffic paths

📋 Requirements
Before running the project, ensure you have:

GNS3 installed and configured.

A compatible Cisco 7200 IOS image.

IOS support for MPLS, MPLS-TE, and RSVP-TE.

Sufficient system resources to run six virtual routers and two VPCS hosts.

[!IMPORTANT]
The Cisco IOS image is not included in this repository. You must provide a legally obtained IOS image with the required MPLS-TE and RSVP-TE capabilities.

▶️ Getting Started
Clone or download this repository.

Open GNS3.

Import mpls-te-path-engineering.gns3project.

Configure the required Cisco IOS image for the routers.

Start the network devices.

Apply the router configurations and test MPLS-TE connectivity.

🎯 Learning Objectives
This lab provides a practical environment to explore:

MPLS label switching and forwarding.

OSPF-based routing in an MPLS core.

RSVP-TE signaling and tunnel establishment.

Explicit-path configuration.

Traffic engineering across alternative network paths.

MPLS-TE tunnel behavior and path verification.

Project: MPLS Traffic Engineering
Platform: GNS3
Router Platform: Cisco 7200
