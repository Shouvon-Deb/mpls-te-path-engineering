# Connectivity Verification

## PC1 → PC2

The endpoint connectivity test was performed from PC1 to PC2.

```text
ping 192.168.2.10
```

The captured test was successful.

## Expected Path

The traffic enters the network through R1 and reaches R6 before being delivered to PC2.
The MPLS-TE implementation provides explicit engineered paths between R1 and R6
