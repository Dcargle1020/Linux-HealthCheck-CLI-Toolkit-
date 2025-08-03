# Linux HealthCheck CLI Toolkit

A modular, command-line-based health check toolkit built for Linux systems. This toolkit is designed to help system administrators, DevOps engineers, and Linux learners quickly assess system health, troubleshoot issues, and maintain uptime with ease.

## 🛠️ Features

- Modular CLI health checks
- Bonus modules for deeper insights
- Easy to extend and automate via cron
- Beginner-friendly commands and output

## 📁 Modules Overview

### 1. CPU Health Check
- **Commands Used:** `uptime`, `top`, `sar -u`, `ps -eLf`
- **Checks:** Load average, CPU usage, runaway processes, thread count
- **Purpose:** Detect CPU bottlenecks and unresponsive processes

### 2. Memory Health Check
- **Commands Used:** `free -h`, `vmstat`, `top`, `ps aux --sort=-%mem`, `smem`
- **Checks:** Memory availability, swap use, per-process memory, OOM killer traces
- **Purpose:** Identify memory leaks, saturation, and optimize swap

### 3. Disk Health Check
- **Commands Used:** `df -h`, `df -i`, `du -sh`, `ncdu`, `find`, `lsof`
- **Checks:** Disk usage, inode exhaustion, large files, deleted open files
- **Purpose:** Detect and prevent storage-related service failures

### 4. Network Health Check
- **Commands Used:** `ip a`, `ip r`, `ping`, `nmcli`, `ethtool`, `nmap`
- **Checks:** Interface status, default gateway reachability, basic network diagnostics
- **Purpose:** Troubleshoot connectivity and local network issues

### 5. Log Cleaner
- **Commands Used:** `find`, `journalctl`, `logrotate`, `du`
- **Tasks:** Clean `/var/log`, truncate large logs, vacuum system journal
- **Purpose:** Maintain log hygiene and reclaim disk space

## 💡 Bonus Modules

### ✅ Uptime Tracker
- **Command:** `uptime`, `who -b`
- **Purpose:** Log and review system uptime and last boot

### 📊 File Descriptor Usage
- **Commands:** `lsof | wc -l`, `cat /proc/sys/fs/file-nr`
- **Purpose:** Monitor and diagnose open file limits and descriptor leaks

### 🔐 Failed Login Attempts
- **Command:** `lastb`, `grep "Failed password" /var/log/auth.log`
- **Purpose:** Monitor brute force attempts and security audit trails

## 🚀 Usage

Run each module individually or create a wrapper script:

```bash
chmod +x cpu_check.sh
./cpu_check.sh
```

To automate with cron:

```bash
crontab -e
```

Then add:

```cron
0 * * * * /path/to/cpu_check.sh >> /var/log/healthcheck.log 2>&1
```

## 📸 Sample Output

See the `/screenshots` directory for output examples for each module:
- CPU load snapshot
- Disk usage alert
- Failed login log
- Open file count

## 🧰 Requirements

- Bash
- `sar` from `sysstat`
- `ncdu`, `smem`, and other system monitoring tools (can be installed via apt/yum)

## 🌟 Why This Project?

Built from hands-on training during a Linux-based system health and troubleshooting lab. Ideal for bootcampers, self-taught engineers, and aspiring DevOps professionals who want to document, debug, and automate the fundamentals.

---

© 2025 Dominique Cargle | Level Up in Tech Bootcamp
