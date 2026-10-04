# Topology Notes

## Network Structure

The project uses six Cisco 7200 routers and two VPCS hosts.

```text
                    R2 ───── R4
                   /           \
                  /             \
PC1 ─────────── R1               R6 ─────────── PC2
                  \             /
                   \           /
                    R3 ───── R5
```

| Device | Role |
|---|---|
| R1 | MPLS-TE ingress |
| R2 | Core router |
| R3 | Core router |
| R4 | Core router |
| R5 | Core router |
| R6 | MPLS-TE egress |

**Path A**

```text
R1 → R2 → R4 → R6
```

**Path B**

```text
R1 → R3 → R5 → R6
```

Design Idea
The two parallel paths provide alternative routes between R1 and R6.
The project uses MPLS Traffic Engineering to explicitly control these paths rather than relying only on normal IP routing decisions.
