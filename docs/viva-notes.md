# Viva Notes

## 1. What is the main purpose of this project?

The purpose is to demonstrate how MPLS Traffic Engineering can control traffic paths using RSVP-TE and explicit LSPs.

Instead of depending only on normal OSPF path selection, the network can use engineered paths between R1 and R6.

---

## 2. What problem does the project address?

Normal IP routing generally selects paths according to routing metrics. This does not always provide the level of control needed when traffic demand changes.

This project demonstrates a way to explicitly control traffic paths and reserve bandwidth using MPLS-TE and RSVP-TE.

---

## 3. Why was MPLS-TE selected?

MPLS-TE was selected because it allows the path of traffic to be engineered according to network requirements rather than relying only on the normal shortest-path decision.

It also supports resource reservation through RSVP-TE.

---

## 4. What is RSVP-TE?

RSVP-TE is an extension of RSVP used for establishing and maintaining traffic-engineered MPLS LSP tunnels.

In this project, it is responsible for signaling the required resources for the MPLS-TE tunnels.

---

## 5. What is an LSP?

LSP stands for Label Switched Path.

It is the path followed by MPLS traffic through the network.

In this project, the LSPs are engineered using explicit paths.

---

## 6. What is the difference between PATH_A and PATH_B?

They are two separate explicitly configured paths between R1 and R6.

PATH_A:

```text
R1 → R2 → R4 → R6
```

PATH_B:

```text
R1 → R3 → R5 → R6
```

The purpose is to demonstrate that traffic can be placed on different engineered paths.

## 7. Why are two paths used?

Two paths make it possible to demonstrate path control and resource separation.

It also provides a foundation for studying how traffic could be distributed when network conditions change.

## 8. What is the role of OSPF?

OSPF provides the underlying IP reachability between the routers.

MPLS-TE is built on top of this routing foundation.

In this implementation, OSPF also carries the traffic-engineering information required by MPLS-TE.

## 9. Why are loopback addresses used?

Loopback interfaces provide stable router identifiers.

In this project, the loopbacks are also used as the MPLS-TE router IDs.

For example:

```text
R1 = 10.255.0.1
R6 = 10.255.0.6
```

## 10. What is Tunnel0?
Tunnel0 is the MPLS-TE tunnel from R1 toward R6 that uses PATH_A.

```text
R1 → R2 → R4 → R6
```

It requests:
```text
1500 kbps
```

## 11. What is Tunnel1?
Tunnel1 is the MPLS-TE tunnel from R1 toward R6 that uses PATH_B.
```text
R1 → R3 → R5 → R6
```

It also requests:
```text
1500 kbps
```

## 12. What does tunnel mpls traffic-eng autoroute announce do?

It allows the MPLS-TE tunnel to be considered in the routing process so that traffic can use the engineered tunnel.

In this project, it helps integrate the TE tunnels with the routing decision.

## 13. What does tunnel mpls traffic-eng bandwidth 1500 mean?

It specifies a requested traffic-engineering bandwidth of 1500 kbps for the tunnel.

RSVP-TE then signals the resource requirement through the selected path.

## 14. What is an explicit path?

An explicit path defines the sequence of addresses that an MPLS-TE tunnel should follow.

For example, PATH_A specifies:
```text
10.0.12.2
10.0.24.2
10.0.46.2
```

This forces the tunnel toward the R1-R2-R4-R6 branch.

## 15. How did you verify that the tunnels were working?
The main verification commands were:
```text
show mpls traffic-eng tunnels tunnel 0
show mpls traffic-eng tunnels tunnel 1
```

The tunnels showed:
```text
Admin: up
Oper: up
Path: valid
Signalling: connected
```

PATH_A was active for Tunnel0 and PATH_B was active for Tunnel1.

## 16. How did you verify RSVP?
The following commands were used:
```text
show ip rsvp interface
show ip rsvp reservation
```

The reservation output showed two 1500K reservations between the R1 and R6 loopback addresses.

## 17. How did you verify OSPF?
The following commands were used:
```text
show ip ospf neighbor
show ip route
```

The OSPF neighbor relationships and learned routes confirmed the underlying IP routing.

## 18. How did you test connectivity?

Connectivity was tested between the endpoint networks.
```text
PC1:
192.168.1.10

PC2:
192.168.2.10
```

ICMP ping between the endpoints was successful.

## 19. Does the project prove that MPLS-TE improves performance?

No.

The current implementation proves that MPLS-TE, RSVP-TE, explicit paths, bandwidth reservation, and tunnel establishment are working.

A controlled traffic-load experiment is still required to quantitatively compare performance against the OSPF baseline.

## 20. What performance metrics could be measured in future work?
The main metrics would be:
```text
- Throughput
- Delay
- Packet loss
- Link utilization
- Path utilization
- Behavior during congestion
```

## 21. What would happen if one engineered path failed?

The current implementation establishes the two paths independently, but a complete automatic failover experiment has not been used as a measured result.

Failover behavior should therefore be tested separately rather than claimed from the current verification.

## 22. What is the difference between MPLS and MPLS-TE?

MPLS provides label-based forwarding.

MPLS-TE extends MPLS to provide control over how traffic-engineered LSPs are established and which paths they use.

## 23. Why is RSVP important in this project?

RSVP-TE provides the signaling mechanism used to establish the traffic-engineered tunnels and reserve the requested bandwidth.

Without the required signaling and available resources, the TE tunnel may not be established.

## 24. What Cisco commands were important for the implementation?

Some of the main configuration commands were:
```text
ip cef
mpls traffic-eng tunnels
mpls traffic-eng area 0
mpls traffic-eng router-id Loopback0
ip rsvp bandwidth
tunnel mode mpls traffic-eng
tunnel mpls traffic-eng bandwidth 1500
tunnel mpls traffic-eng path-option 1 explicit name PATH_A
tunnel mpls traffic-eng path-option 1 explicit name PATH_B
```

25. What is the main limitation of the current project?

The project currently focuses on implementation and verification.

It does not yet contain a controlled quantitative comparison between normal OSPF routing and MPLS-TE under generated congestion.

That experiment would be the next major extension.
