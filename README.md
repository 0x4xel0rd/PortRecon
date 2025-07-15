# PortRecon
Nmap offers a rich set of scanning techniques—from lightning-fast top-port checks to deeply thorough vulnerability and service enumeration—but chaining them manually can be tedious and error-prone. This script automates a logical progression of scans, starting with the quickest TCP port sweep and common UDP probe, then moving on to a comprehensive all-port scan with open-port extraction, and finally performing in-depth version, script, and vulnerability checks against only the discovered services. By structuring the workflow from faster to slower, you’ll get immediate, actionable results early on, while still capturing all the detailed intelligence you need for a full assessment.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# PortRecon.sh - Nmap Scan Automator
A simple Bash script to automate common Nmap scans against one or more targets. Saves results to per-host output files and provides a step-by-step overview of:

1. Top TCP ports scan  
2. Common UDP ports scan  
3. Full TCP port scan + open-port extraction + version/OS/script scan  
4. Detailed “everything” scan (vuln scripts, OS detection, version detection) against open ports  

---

## Features

- **Batch scanning**: Pass multiple IP addresses/hostnames in one go  
- **Top TCP scan**: Quickly enumerate the most common TCP ports  
- **UDP scan**: Checks common UDP services  
- **Full TCP port scan**: Scans all 65,535 TCP ports, extracts open ports  
- **Version & default scripts**: Runs `-sV` and `-sC` against open ports  
- **Detailed vulnerability scan**: Runs `-A --script=vuln` for in-depth enumeration  
- **Timestamps & logs**: Appends all output to `<target>_nmap_scan_results.txt` and XML to `<target>_nmap_output`  

---

## Prerequisites

- **Bash** (v4+)  
- **Nmap** (v7.80+) installed and in your `PATH`  
- Sufficient permissions (run as root or via `sudo` for UDP scanning and OS detection)  

---

## 📦 Installation

Clone the repo or download the script:

```bash
   git clone https://github.com/0x4xel0rd/PortRecon.git
   cd PortRecon

   chmod +x PortRecon.sh
   ./PortRecon.sh <TARGET1> [TARGET2 ... TARGET_N]
   Example: ./PortRecon.sh 192.168.1.10 example.com 10.0.0.5
```

