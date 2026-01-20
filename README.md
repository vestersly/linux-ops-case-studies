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

- **01 — VM-to-VM authenticated connectivity (VirtualBox)**  
  → [View case study](case-studies/01-vm-to-vm-authenticated-connectivity.md)

- **02 — Disk pressure causing systemd service failure**  
  → [View case study](case-studies/02-disk-pressure-systemd-service-failure.md)

- **03 — CPU pressure causing service degradation**
  → [View case study](case-studies/03-cpu-pressure-service-degradation.md)


