# Firewall Task - Cyber Security Internship

## Objective
Configure and test basic firewall rules to allow or block network traffic.  
Specifically: block inbound Telnet traffic on **port 23**, test it, and restore original state.  

---

## 🔹 Linux (UFW)

### Steps Performed
1. Installed and enabled UFW.
   ```bash
   sudo apt update
   sudo apt install ufw -y
   sudo ufw enable
   ```
2. Allowed SSH to avoid lockout.
   ```bash
   sudo ufw allow ssh
   ```
3. Added a rule to block Telnet (port 23).
   ```bash
   sudo ufw deny 23/tcp
   ```
4. Verified rules.
   ```bash
   sudo ufw status verbose
   ```
5. Tested connection to port 23.
   ```bash
   nc -vz localhost 23
   ```
   → Output showed **connection refused/blocked**. 
6. Removed the deny rule to restore state.
   ```bash
   sudo ufw delete deny 23/tcp
   ```

### Screenshots
- `linux/screenshots/ufw-status.png` → shows UFW with port 23 blocked.  
- `linux/screenshots/nc-test.png` → shows connection attempt to port 23 failed.  
