# Nmap

> nmap machine-ip scanme.nmap.org example.com
> 
> nmap 10.12.12.13-20
> 
> nmap machine-ip/30
>
> nmap -il list-of-hosts.txt
>
> nmap -sL TARGETS   -> list of hosts nmap will scan
> 
> n to not Nmap to DNS server to find the names (reverese DNS resolution on all the targets)


...

1. ARP scan
2. ICMP scan
3. TCP/UDP scan

1. arp-scan
2. masscan

nmap - network mapper
1. enumurate targets
2. discover live hosts
3. reverse dns lookup
4. scan ports
5. detect versions
6. detect os
7. traceroute
8. scripts
9. write output

**Subnetworks**
- /16    255.255.0.0 with 65000 hosts
- /24    255.255.255.0 with 250 hosts

- arp queires cannot be routed out of the subnet / cnanot cross the subnet router
- ARP is a link layer protocol

**ENumurating targets**
1. list machine-ip scanme.nmap.org example .com
2. range 10.10.11.15-20
3. subnet 10.10.10.10/30 scan 4 ip addresses
4. nmap -iL lists-of-hosts.txt
5. nmap -sL TARGETS - lists the hosts nmap can scan without scanning, however does a revereser DNS resolution to get their names ( add -n if you dont want names) (discovers online hosts withpout port scanning)


**Discovering live hosts**

OSI:
1. physical layer
2. data link layer
3. network layer
4. transport layer
5. session layer
6. presentation layer
7. application layer

TCP/IP:
1. link layer - ARP, ethernet(802.3), wifi(802.11), DSL, bluetooth
2. network layer - IPv4, IPv6, ICMP, IPsec
3. transport layer - tcp/udp
4. application layer - http/https, smtp, pop3, imap, ssh, ftp, snmp, telnet, rdp

arp - link layer - sending a frame to broadcast 
icmp - network layer - type8(echo), type0(echo reply)
tcp/udp - transport layer - use when icmp echo is blocked using a crafted packet to common tcp/udp ports


**Nmap host discovery using ARP**
- nmap -sn TARGETS (discover online hosts without port scanning)
- ARP requests on a local network for a priviledged user
- ICMP echo requests, TCP ACK to port 80, TCP SYN to port 443, ICMP timestamp request if target is outside of network
- unprividged user: uses TCP-3 way handshake by sending   SYB packets to 80 and 443 for targets outside of network
- if you want namp to do ARP scan only and without port scanning **nmap -PR -sn TARGETS** where PR refers to "only ARP" and -sn ferests to "no port scan"

- arp-scan --localnet or arp-scan -l ( to send ARP queries to all valid IP address on the local network)
- if more interface like eth0, eth1 then use this command to check the spcefic interface **sudo arp-scan -I eth0 -l**
- apt install arp-scan
- arp-scan machine-ip/24
- arp-scan and nmap -PR -sn yield similar traffic patterns form packet capture


**Nmap host discovery using ICMP**
- ping(icmp type 8/echo) and ping reply(icmp type0)
- PE if you want icmp option and -sn if you dont want port scan
- nmap -PE -sn TARGET
- many firewalls block icmp
- sudo nmap -PE -sn machine-ip/24
- it will try with the ARP first and retun the live ip with mac address
- if it is by ICMP , then mac address wont be displayed

- since ICMP echo requests are blocked, we can use ICMP timestamp(type 13) or ICMP Address mask request
- icmp toimestamp reply (type 14)
- PP option for ICMP timestamp request to find ths system is online
- **nmap -PP -sn machine-ip/24**

- address mask reply (type 18)
- PM
- nmap -PM -sn TARGETS
- **namp -PM -sn machine-ip/24**


**Nmap host discovery using TCP/UDP**
  - if we send TCP SYN packet to tcp port 80, an open port should reply with a   SYN/.ACK flag, a closed port will result in a RST (reset)
  - PS to use TCP SYN ping
  - PS followed by port number, range, list or a combination of them
  - PS21
  - PS21-25
  - PS80,443,8080
  - priviledged users doesnt need to complete the tcp-3 way handshake even if the port is open
  - unpriviledged users must complete the tcp-3 way handshake if the port is open
  - **nmap -PS -sn TARGET**
  - nmaep -PS -sn machine-ip/24

  - TCP ACK ping - for priviledged user only (unporiviledged user will initiate a 3 way handshake if they try this)
  - PA
  - PA21
  - PA21-25
  - PA80,443,8080
  - DEFAULT PORT IS 80
  - nmap -PA -sn TARGET
  - if the TCP packet back with RST flag, then open

  - UDP ping:
    - udp packet to an open port is not expected to any reply
    - but if we send a udp packet to a closed udp port - ICMP port unreachable packet
    - PU
    - nmap -PU -sn TARGET

  - MASSCAN:
    - p
    - p followed by port number, list, range
    - masscan machine-ip/24 -p443
    - masscan machine-ip/24 -p80,443
    - p22-25
    - masscan machine-ip/24 --top-ports 100
    - apt install masscan



**Using Reverse DNS lookup**
- n to skip
- by default nmap will query the dns server
- R to query the dns server even for offline hosts
- --dns-servers DNS_SERVER   for specific DNS server