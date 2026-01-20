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


