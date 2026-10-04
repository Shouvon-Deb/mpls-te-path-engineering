# MPLS-TE Tunnel Verification

## Check All TE Tunnels

```text
show mpls traffic-eng tunnels
```

**Check Tunnel 0**

```text
show mpls traffic-eng tunnels tunnel 0
```

**Expected engineered path:**

```text
R1 → R2 → R4 → R6
```

**Important state:**

```text
Admin up
Oper up
Path valid
Signalling connected
```

**Check Tunnel 1**

```text
show mpls traffic-eng tunnels tunnel 1
```

**Expected engineered path:**

```text
R1 → R3 → R5 → R6
```

**Important state:**

```text
Admin up
Oper up
Path valid
Signalling connected
```

**OSPF Verification**

```text
show ip ospf neighbor
```

**Routing Verification**

```text
show ip route
```
