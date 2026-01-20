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
