# Case Study 05 — Process Resource Limits Causing Service Failure

---

## Failure Flow (ASCII)

```text
Application / Service
        |
        v
 OS-enforced resource limits (ulimit / cgroups)
        |
        v
 Resource threshold exceeded
        |
        v
 Kernel denies allocation
        |
        v
 Application error or crash
        |
        v
 Service disruption

---

## Detection & Symptoms

The service began returning intermittent errors and failed to handle new requests under normal traffic levels.

Service restarts provided only temporary relief, with failures recurring shortly after startup.

System monitoring showed normal CPU utilization, available memory, and sufficient disk space, making the failure non-obvious from standard host-level metrics.

---

## Investigation & Findings


Initial investigation focused on common system-level bottlenecks, including CPU saturation, memory exhaustion, and disk I/O pressure. None of these metrics showed abnormal behavior during the time of the failures.

Application logs, however, indicated repeated errors when attempting to spawn new processes and open additional file descriptors.

Further inspection of the running service revealed that it was operating under restrictive operating system–enforced resource limits. These limits were reached during normal workload conditions, despite the host system having sufficient available resources.

Once the defined limits were exceeded, the kernel denied further resource allocation requests, leading to application-level errors and eventual service instability.

---

## Root Cause Analysis

The root cause of the service failure was the enforcement of restrictive process-level resource limits configured at the operating system level.

These limits constrained the number of processes and file descriptors available to the service, causing it to exhaust allowable resources during normal operation.

Once the limits were reached, the Linux kernel denied further allocation requests, leading to application errors and repeated service failures despite sufficient system-wide resources.

