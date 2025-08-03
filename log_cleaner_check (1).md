# 🧹 Log Cleaner Module Report

## 🔍 Commands Run
- `journalctl --vacuum-time=2d`
- `find /var/log -name "*.gz" -mtime +7 -exec rm -f {} \;`
- `du -sh /var/log`
- `logrotate -f /etc/logrotate.conf`

## 📁 Space Recovered
- Log directory cleaned successfully.
- Old logs and compressed logs removed.

## 🛠️ Actions Taken
- Forced logrotate.
- Pruned systemd journal logs older than 2 days.

## ✅ Summary
Logs were successfully cleaned and disk space usage reduced. Future improvements include automating cleanup via cron or systemd timers.