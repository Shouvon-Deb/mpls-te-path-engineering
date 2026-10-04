# GNS3 Project

This folder contains the portable GNS3 project used to build and test the MPLS Traffic Engineering lab.

## Project

`mpls-te-path-engineering.gns3project`

### Network

- 6 × Cisco 7200 routers
- 2 × VPCS hosts
- OSPF
- MPLS
- MPLS-TE
- RSVP-TE
- 2 explicit TE paths
- 2 TE tunnels

### Paths

**PATH_A**

```text
R1 → R2 → R4 → R6
```

**PATH_B**

```text
R1 → R3 → R5 → R6
```

The Cisco IOS image is not included. A legally obtained IOS image with the required MPLS-TE/RSVP-TE capabilities is required to run the project.
