# HTB Academy: Attacking Web Applications with Ffuf

**Status:** ✅ Completed  
**Difficulty:** Easy (Tier 0)  
**Badge Earned:** Fuzzing is power (Top 1.4% of users)

---

## 📘 Module Key Takeaways
Based on the official HTB Academy syllabus, this module covered practical implementation of web application fuzzing, including:
*   **Directory & Page Enumeration:** Discovering hidden web structure and files.
*   **Vhost & Subdomain Discovery:** Uncovering hidden virtual hosts and infrastructure.
*   **Parameter Fuzzing:** Finding hidden GET/POST PHP parameters.
*   **Value Fuzzing:** Brute-forcing parameter values to extract data.

---

## 🛠️ Core Commands Mastered

### 1. Directory Fuzzing
Used to discover hidden folders on a web server:
```bash
ffuf -w /usr/share/wordlists/dirb/common.txt -u http://[Target_IP]/FUZZ
```

### 2. Page & Extension Fuzzing
Used to find specific file types (like `.php` or `.html`):
```bash
ffuf -w /usr/share/wordlists/dirb/common.txt -u http://[Target_IP]/FUZZ -e .php,.html,.txt
```

### 3. Subdomain & Vhost Fuzzing
Used to identify hidden subdomains that might hold development or admin panels:
```bash
# Vhost Fuzzing
ffuf -w /usr/share/wordlists/secclists/Discovery/DNS/subdomains-top1million-5000.txt -u http://[Target_IP]/ -H "Host: FUZZ.target.local"
```

### 4. Parameter Fuzzing (GET Requests)
Used to discover hidden parameters in a URL:
```bash
ffuf -w /usr/share/wordlists/secclists/Discovery/Web-Content/burp-parameter-names.txt -u http://[Target_IP]/index.php?FUZZ=key
```

---

## 🎯 Practical Application
Throughout the guided exercises, I practiced using command-line filters (like `-fc` to filter HTTP status codes or `-fs` to filter out specific page sizes) to cut through background noise and isolate valid data vulnerabilities efficiently.
