# Lab: Network Enumeration & Service Discovery

### **1. Objective**
Perform active reconnaissance to map the attack surface and identify specific service versions for vulnerability mapping.

### **2. Execution**
* **Tool:** Nmap
* **Command:** `nmap -sV -O 192.168.1.2`
* **Findings:** Identified Port 80 (Apache 2.2.8), Port 445 (Samba), and Port 3306 (MySQL) active.

### **3. Proof of Concept**
* **Output:** `nmap-results.txt`
* **Screenshot:** ![Nmap Scan](nmap_results_screenshot.png)

### **4. Mitigation Strategy**
* **Service Hardening:** Disable unnecessary services (SMB/MySQL) on public-facing interfaces.
* **Firewalling:** Implement a Host-based Intrusion Prevention System (HIPS) or firewall to restrict port access to authorized management IPs only.
* **Information Throttling:** Disable banner grabbing by configuring `ServerTokens Prod` and `ServerSignature Off` in the web server config to hide version numbers.
