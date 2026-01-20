# Case Study 04 — Memory Pressure Causing OOM Kill

---

## Failure Flow (ASCII)

```text
Application / Service
        |
        v
 systemd service
        |
        v
 Process memory allocation
        |
        v
 Physical RAM exhausted
        |
        v
 Swap heavily used / exhausted
        |
        v
 Kernel OOM Killer triggered
        |
        v
 Process terminated (SIGKILL)
        |
        v
 Service interruption / restart
