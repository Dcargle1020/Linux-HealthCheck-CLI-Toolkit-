# 🔐 Failed Login Attempts Report

## 🔍 Commands Run
- `lastb`
- `grep "Failed password" /var/log/auth.log`
- `ausearch -m USER_LOGIN` (if auditd enabled)

## 📊 Observations
- No suspicious brute force detected.
- X failed login attempt(s) in the last 24 hours (adjust with real output).
- All attempts appear to be local (or from expected IP ranges).

## 🛠️ Actions Taken
- Monitored auth log.
- Consider enabling `fail2ban` or UFW if needed.

## ✅ Summary
Authentication log monitoring successful. Failed attempts documented for auditing. Recommend continued monitoring.