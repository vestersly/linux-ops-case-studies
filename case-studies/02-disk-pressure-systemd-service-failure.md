### Failure Flow (ASCII)

```text
Application / Service
        |
        v
   systemd service
        |
        v
   Log files (/var/log)
        |
        v
   Root filesystem (/)
        |
   [DISK FULL / INODE EXHAUSTED]
        |
   systemd restart loop / service failure

---

## How This Case Study Was Created

This case study was intentionally created in a **controlled lab environment**
to simulate a real-world production failure scenario involving disk pressure
and `systemd` service instability.

The goal is to demonstrate **how disk exhaustion impacts service behavior**,
how the issue is diagnosed, and how it is safely resolved.

> ⚠️ All steps below were performed on test virtual machines only.

---

## Reproduction Steps (Controlled Failure)

### Step 1: Verify initial disk state

Confirm that sufficient disk space is available before inducing pressure:

```bash
df -h

