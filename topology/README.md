# Topology

This folder documents the network topology and IP addressing used by the project.

## Files

| File | Purpose |
|---|---|
| `addressing-plan.md` | Complete IP addressing reference |
| `topology-notes.md` | Topology structure and path design |

## Network Structure

The topology contains six routers and two endpoint PCs.

```text
                 R2 ───── R4
                /           \
              R1             R6
                \           /
                 R3 ───── R5
```

## The two main engineered paths are:
```text
PATH_A: R1 → R2 → R4 → R6

PATH_B: R1 → R3 → R5 → R6
```
