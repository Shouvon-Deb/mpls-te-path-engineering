# Implementation Notes

## Project

MPLS Traffic Engineering for Improved Bandwidth Utilization Under Changing Network Conditions.

## Environment

The implementation was built in GNS3 using six Cisco 7200 routers and two VPCS hosts.

## Technologies

- OSPF
- MPLS
- MPLS Traffic Engineering
- RSVP-TE
- Explicit TE paths

## TE Paths

### PATH_A

```text
R1 → R2 → R4 → R6
```

### PATH_B

```text
R1 → R3 → R5 → R6
```

## Tunnel Configuration

Two TE tunnels were established from R1 to R6.
Each tunnel was configured with:

```text
1500 kbps
```

## Verification
The implementation was verified using:

```text
show mpls traffic-eng tunnels
show ip rsvp interface
show ip rsvp reservation
show ip ospf neighbor
show ip route
```

End-to-end connectivity was verified using:

```text
ping 192.168.2.10
```

## Current Scope
The current implementation demonstrates TE tunnel establishment, explicit path control, RSVP reservation and connectivity.
A controlled high-load performance comparison is not claimed because the captured evidence does not contain a completed quantitative baseline-versus-TE experiment.
Future testing can measure throughput, delay, packet loss and interface utilization under controlled traffic conditions.
