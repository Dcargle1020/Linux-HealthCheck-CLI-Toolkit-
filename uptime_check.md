# 🕒 Uptime Check Report

### ✅ Module: `uptime_check.sh`  
This module checks the current system uptime and load average using the `uptime` command.

---

### 🔧 Commands Used:
```bash
uptime
```

---

### 📊 Output Sample:
```
22:05:38 up 1 day, 23:20,  3 users,  load average: 0.00, 0.00, 0.00
```

---

### 🧠 What It Does:
- Displays how long the system has been running
- Shows the number of active users
- Reports system load averages over the last 1, 5, and 15 minutes

---

### 📝 Why It Matters:
This is a fast and simple diagnostic tool to:
- Check if the server has rebooted recently
- Identify prolonged uptime (which could indicate missed updates or memory leaks)
- Assess whether the system is under high load

---

### 💡 Notes:
- Load average values close to or above the number of CPU cores might indicate a bottleneck.
- This script outputs clean Markdown you can include in reports or logs.