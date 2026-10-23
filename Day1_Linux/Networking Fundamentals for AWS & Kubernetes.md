1. Find Your Server IP
     > ip addr or ip a
   shows:
     >  IP Address Subnet Mask Network Interface
     Example: 192.168.1.10

2.Check Connectivity
     > ping google.com
     Purpose: Verifies network connectivity, Tests DNS resolution
     stop: Ctrl + C
 3. DNS Lookup   
     > nslookup google.com
     > output:  Name: google.com
               Address: 142.250.x.x
     >purpose Converts domain to IP
Interview favorite:

What happens when you enter google.com in a browser?
```
Browser
→ DNS Lookup
→ IP Address
→ TCP Connection
→ HTTP/HTTPS Request
→ Response
```
      
