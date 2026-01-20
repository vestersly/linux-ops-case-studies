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

## Incident Summary

A production service became unavailable even though system-level monitoring showed no critical CPU, memory, or disk pressure.

Initial checks suggested the host was healthy, but the service continued to fail under normal load.

Further investigation revealed that the service process was hitting operating system–enforced resource limits, preventing it from allocating required resources and causing repeated failures.

