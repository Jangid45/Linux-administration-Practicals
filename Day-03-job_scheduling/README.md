# Day-03: Job Scheduling in Linux

## Objective
To understand and practice job scheduling using:
- AT Job Scheduler
- Cron Job Scheduler
- Systemd service management

---

# 1️. AT Job Scheduler

## Check AT Service Status

```bash
systemctl status atd
```

If not installed:

```bash
dnf install at -y
systemctl enable atd
systemctl start atd
```

---

## Schedule a Job

```bash
at now + 3 minutes
```

Inside AT prompt:

```bash
useradd alex
mkdir /alex_home
usermod -d /alex_home alex
chmod 700 /alex_home
```

Press:

```
Ctrl + D
```

---

## Check Scheduled Jobs

```bash
atq
```

---

## Remove Scheduled Job

```bash
atrm <job_id>
```

Example:

```bash
atrm 5
```

---

## Check AT Logs

```bash
journalctl -u atd
```

Or:

```bash
grep atd /var/log/messages
```

---

# 2️. Cron Job Scheduler

## Check Cron Service

```bash
systemctl status crond
```

Enable and Start:

```bash
systemctl enable crond
systemctl start crond
```

Restart Cron:

```bash
systemctl restart crond
```

Check Status:

```bash
systemctl is-active crond
systemctl is-enabled crond
```

---

## Create a Cron Job

Edit crontab:

```bash
crontab -e
```

Example (runs every 5 minutes):

```bash
*/5 * * * * echo "Hello Linux" >> /home/alex/test.txt
```

---

#  Difference Between AT and Cron

| AT | Cron |
|----|------|
| Executes job once | Executes repeatedly |
| Used for one-time tasks | Used for recurring tasks |
| Command: at | Command: crontab |

---

# Conclusion

Successfully practiced:
- AT job scheduling
- Cron job scheduling
- Service management using systemctl
- Log verification
