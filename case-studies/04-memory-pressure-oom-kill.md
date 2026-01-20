
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

