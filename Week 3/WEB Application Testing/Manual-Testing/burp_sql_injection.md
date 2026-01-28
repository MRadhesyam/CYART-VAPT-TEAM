**Manual SQL Injection (Burp Suite)**

Steps:
1. Intercept request using Burp Proxy
2. Send request to Repeater
3. Modify parameter: ' OR 1=1#
4. Forward request

Result:
- SQL Injection successful
