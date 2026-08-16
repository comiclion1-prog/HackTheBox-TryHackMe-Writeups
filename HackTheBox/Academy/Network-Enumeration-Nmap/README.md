# HTB Academy: Network Enumeration with Nmap

**Status:** ✅ Completed  
**Difficulty:** Easy (Tier 1)  
**Badge Earned:** The eye that sees all 👁️

---

## 📘 Module Key Takeaways
Based on the official HTB Academy syllabus, this module covered deep-dive network reconnaissance methodologies, including:
*   **Host Discovery:** Identifying live hosts across networks without triggering alerts.
*   **Service & OS Detection:** Fingerprinting open ports to discover software versions and underlying operating systems.
*   **Nmap Scripting Engine (NSE):** Leveraging built-in scripts to automate vulnerability detection.
*   **Firewall & IDS Evasion:** Crafting stealth scans to bypass security architecture and obtain accurate results.

---

## 🛠️ Core Scanning Profiles Mastered

### 1. Fast Initial Reconnaissance
Used to quickly scan all 65,035 ports for active services while managing network traffic speed:
```bash
nmap -p- --min-rate 5000 -sV -sC -oN initial_scan.txt [Target_IP]
```

### 2. Aggressive OS & Service Fingerprinting
Leverages deep analysis to determine operating system versions and service details:
```bash
nmap -O -sV -A -T4 -oN aggressive_scan.txt [Target_IP]
```

### 3. Vulnerability Scanning with NSE
Using specific Nmap Scripting Engine categories to hunt for easy wins or misconfigurations:
```bash
nmap --script vuln -p 80,443 [Target_IP]
```

### 4. Advanced Firewall Evasion
Techniques used to bypass firewalls or Intrusion Detection Systems (IDS), such as fragmenting packets (`-f`) or using specific source ports:
```bash
# Fragmenting packets and using a specific source port (e.g., DNS port 53)
nmap -sS -f --source-port 53 -Pn [Target_IP]
```

---

## 🎯 Practical Application
During the module's final skills assessment, I successfully demonstrated the ability to save scan outputs into standard text formats (`-oN`) and XML formats (`-oX`) to parse data, cross-reference service versions against public exploit databases, and chain enumeration findings into actionable attack paths.
