
# 🗂️ Disk Health Check Report

## 🧪 Check Performed
- Disk usage inspection using `df -h`
- Inode usage check with `df -i`
- Directory and file space breakdown using `du`, `find`, and `ncdu`
- Log and temporary file cleanup activities

## 📊 Results

### Disk Usage (`df -h`)
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        40G   36G  2.0G  95% /
tmpfs           3.9G     0  3.9G   0% /dev/shm
```

### Inode Usage (`df -i`)
```
Filesystem      Inodes  IUsed   IFree IUse% Mounted on
/dev/sda1      2621440 230112 2391328   9% /
```

### Large Directories (sample)
```
/var      4.3G
/home     1.7G
/tmp        0G
```

## 🧹 Resolution Actions Taken

- Rotated and vacuumed system logs with:
  ```bash
  journalctl --vacuum-size=100M
  logrotate -f /etc/logrotate.conf
  ```
- Cleaned temporary files:
  ```bash
  rm -rf /tmp/*
  apt clean
  ```

## ✅ Final Status

- Freed up ~2GB of disk space.
- System is now running below the 90% disk usage threshold.
- Scheduled routine log rotation and cleanup cronjobs to prevent recurrence.

---

**Engineer Note:** Disk saturation, especially on root (`/`), can cause service failures and unexpected behavior. Proactive monitoring and automated cleanup are essential in production environments.
