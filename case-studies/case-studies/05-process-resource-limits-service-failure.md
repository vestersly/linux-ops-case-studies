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

