# Addressing Plan

## Loopback Addresses

| Router | Loopback |
|---|---|
| R1 | 10.255.0.1/32 |
| R2 | 10.255.0.2/32 |
| R3 | 10.255.0.3/32 |
| R4 | 10.255.0.4/32 |
| R5 | 10.255.0.5/32 |
| R6 | 10.255.0.6/32 |

---

## Router-to-Router Links

| Link | Network |
|---|---|
| R1–R2 | 10.0.12.0/30 |
| R1–R3 | 10.0.13.0/30 |
| R2–R4 | 10.0.24.0/30 |
| R3–R5 | 10.0.35.0/30 |
| R4–R6 | 10.0.46.0/30 |
| R5–R6 | 10.0.56.0/30 |

---

## End Hosts

| Device | IP Address | Gateway |
|---|---|---|
| PC1 | 192.168.1.10/24 | 192.168.1.1 |
| PC2 | 192.168.2.10/24 | 192.168.2.1 |

---

## MPLS-TE Paths

### PATH_A

```text
R1 → R2 → R4 → R6
```
### PATH_B

```text
R1 → R3 → R5 → R6
```

TE Tunnel Bandwidth
1500 kbps
