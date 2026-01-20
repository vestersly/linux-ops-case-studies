# Linux Ops Case Studies (SRE-style)

This repository documents **operational Linux troubleshooting** performed in a virtualized environment using:

- **Host OS:** Ubuntu 22.04  
- **Hypervisor:** Oracle VirtualBox  
- **Guest VMs:** Kali Linux & Ubuntu Linux  

The focus is not tooling, but **how Linux systems fail, how they are diagnosed, and how they are stabilized** — using an incident-driven, SRE-style approach.

---

## What This Repository Demonstrates

- Linux OS-level reasoning (processes, memory, disk, services)
- VM-to-VM networking and isolation troubleshooting
- Authentication and trust establishment between systems
- systemd service analysis and recovery
- Disk and CPU pressure diagnosis
- Preventive thinking (monitoring, limits, operational discipline)

Each case study follows the same structure:

**Symptoms → Hypotheses → Evidence → Fix → Verification → Prevention → AWS Mapping**

---

## Case Studies

> 🚧 Case studies are added incrementally to reflect real operational scenarios.

- **01 — VM-to-VM authenticated connectivity (VirtualBox)** — documented operational scenario


---

## Cloud & AWS Relevance

Although executed locally, these scenarios map directly to:
- **AWS EC2** (instance-level troubleshooting)
- **VPC networking** (reachability & isolation)
- **Security Groups / IAM trust models**
- **SRE / DevOps operational workflows**

This repository is maintained as a **living operational portfolio**, not a
