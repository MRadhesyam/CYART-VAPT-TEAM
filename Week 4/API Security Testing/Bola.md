**Broken Object Level Authorization (BOLA)**

Platform: PortSwigger Web Security Academy

Steps:
- Intercepted API request via Burp
- Modified object ID in filename (3.txt → 1.txt)
- Retrieved unauthorized data
- Extracted credentials
- Logged in as another user

Result:
- BOLA vulnerability confirmed
