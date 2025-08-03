
# 🧠 CPU Health Check Report

## 🛠 Module: cpu_check.sh

### ✅ Purpose:
This script evaluates CPU usage trends and identifies resource-heavy processes to monitor or mitigate bottlenecks.

---

## 📊 Sample Output:
```
--- CPU Usage (top 5 processes) ---
  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND
  817 ubuntu    20   0   80936   3120   2576 R  35.0  0.3   0:01.23 stress
  818 ubuntu    20   0   80936   3120   2576 R  34.7  0.3   0:01.22 stress
  819 ubuntu    20   0   80936   3120   2576 R  34.3  0.3   0:01.21 stress
  820 ubuntu    20   0   80936   3120   2576 R  34.0  0.3   0:01.20 stress
```

### 🔍 Key Metrics:
- High CPU utilization by `stress` processes.
- Indicates CPU saturation under artificial load testing.

---

## 🧾 Interpretation:
- The system is under sustained high CPU load, likely from a stress test or runaway process.
- Useful to confirm if services or applications are over-consuming CPU.

---

## ✅ Recommended Actions:
- Terminate or renice high %CPU processes if they are non-essential.
- Consider load balancing or scaling if this is a production system.
- Implement monitoring/alerts using tools like `top`, `htop`, `uptime`, `sar`, or `Glances`.

---

## 📂 Related Commands Used:
- `top`
- `ps aux --sort=-%cpu | head`
- `uptime`
- `sar -u 1 3` (if `sysstat` is installed)
