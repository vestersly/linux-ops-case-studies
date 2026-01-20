
# Case Study 04 — Memory Pressure Causing OOM Kill

---

## Failure Flow (ASCII)

```text
Application / Service
        |
        v
 Memory allocation requests
        |
        v
 Linux memory manager
        |
   [MEMORY PRESSURE]
        |
        v
 Out-Of-Memory (OOM) condition
        |
        v
 OOM Killer selects victim process
        |
        v
 Process terminated (SIGKILL)
        |
        v
 Service disruption / crash


---

## Symptoms

- Application or service abruptly terminated
- No graceful shutdown or error message
- System logs show unexpected process death
- Service becomes unavailable under load

---

## Hypotheses

- The system exhausted available memory
- Swap space was insufficient or unavailable
- Kernel invoked the OOM killer to recover memory
- A critical service process was selected as the victim

---

## Evidence

- `dmesg` and `journalctl` show OOM killer activity
- Kernel logs identify the killed process and memory usage
- Memory statistics show near-zero available RAM
- Process termination signal is `SIGKILL`

---

## Fix

- Restart the affected service
- Reduce memory consumption of applications
- Add or resize swap space
- Apply memory limits to non-critical processes
- Tune application memory usage

---

## Verification

- System memory returns to stable levels
- No further OOM events appear in kernel logs
- Services remain running under normal load
- Monitoring shows healthy memory headroom

---

## Prevention

- Implement memory monitoring and alerting
- Configure swap appropriately
- Use cgroups or container limits
- Avoid unbounded memory allocation
- Load test applications before production

---

## AWS Mapping

- EC2 instance memory exhaustion
- CloudWatch memory alarms
- ECS / EKS container memory limits
- OOMKilled pods in Kubernetes
- Auto Scaling triggered by memory pressure


