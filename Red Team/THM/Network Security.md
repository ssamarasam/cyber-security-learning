# Network Security

## Passive Reconnaissance

### Passive reconnaissance
- whois, nslookup, dig

Whois:
- rfc 3912 specification
- 


whois tryhackme.com

nslookup -type=A tryhackme.com 1.1.1.1

dig @1.1.1.1 tryhackme.com MX


- DNSdumpster


### Shodan.io



## Active reconnaissance

- ping, traceroute, telnet, nc  - to gather information about network, system and devices
- can be phone call, visit to company, visit website, checking if firewall has an open SSH port open

**Web browser**
- cntl + shift + i  -> dev tools
- foxyProxy
- UserAgent Switcher and Manager - gives you the ability to pretend to accessing the webpage from a different operating system or different browser (web brpser to iphones mobile brower switch)
- Wappalyzer - insights about the technologies used in the website

**PING**
- ping -c 10 11.12.13.14
- ping -n 10 11.12.13.14   -> for windows machines
- by default windows firewall blocks the PING request
- -s for packet size
- ICMP header size 8

**Traceroute**
- finds the IP address of the routers or hops that a packet traverses as it goes from your system to a target host
- finds the number of routers between the two systems
> linux:     traceroute machine-ip
> windows:   tracert machine-ip
>
> traceroute tryhackme.com


**Telnet**
- communicate rempotely - unsecured since the packets are not encrypted during transmit
> telnet 10.11.12.13 80
> GET / HTTP/1.1
> host: telnet  -> double enter
- above prints the server installed with its version along with few other details

**Netcat**
- nc
- supports both TCP and UDP protocols
- can function as a client that connects to a listening port
- can function as a server that listens on a port of your choice
- nc ip-address PORT --> SHIFT+ENTER after 

> nc 101.11.12.23 80
> GET / HTTP/1.1
> host: netcat

to open a server and listen to a port
> nc -lp 1234
> nc -vnlp 1234 equaivalent to nc -v -n -l -p 1234
>
- l - listening mode
- p - specifying port number  => p should appear just before the port number
- n - numeric only - no resolution of hostnames via DNS  - this option will avoid any DNS lookups and warnings
- v - verbose output - to discover any bugs / optional
- vv - very verbose / optional
- k - keep listening after client disconnects
> port numbers less than 1024 reuire root privileges to listen on






























