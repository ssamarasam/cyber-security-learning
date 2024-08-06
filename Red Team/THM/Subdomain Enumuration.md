# Subdomain enumuration
- finding valid subdomains within the domain
- to expand attack surface to try and discover more potential points of vulnerability

1. brute force
2. OSINT
3. Virtual Host


### OSINT - SSL/TLS certificates
- CA does CT certificate Transparency logs - publically acecssible logs of every ssl/tls certificate created for the domain
- to stop malicious and accidentaly made certificates from being used
- ites like https://crt.sh and https://ui.ctsearch.entrust.com/ui/ctsearchui offer a searchable database of certificates that shows current and historical results.

### OSINT - search engines
-   -site:www.domain.com site:*.domain.com  -> brings all the subdonmain names beloging to domain

### DNS brute force
- method of trying tens, millions of different possible subdomains from a pre-defined list of commonly used subdomain names
- require many requests - so automate it with tools
- tool: dnsrecon
> dnsrecon -t brt -d acmeitsupport.thm   - list the subdomain names associatd with it

### OSINT sublist3r
- automation tool to dicover subdomains
> ./sublist3r.py -d acmeitsupport.thm   - it searhes sub domain anems in various sites

### Virtual Hosts
- some subdomains are not hosted in publically accessible DNS resuls
- it might be stored in private dns server or recorded on developer machine in their etc/hosts
- c:\windows\system32\drivers\etc\hosts file for windows users - which maps domain names to IP address
- because server can host many sites form a single server and it knows which site is requested from client HOST header
- make changes to host header and check the response to see if we discovered new website
- >            
user@machine$ ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u http://10.10.147.83 -fs {size}

  - form thw rodlist, it replaces the FUZZ and searches the subdomains
  - fs {size} - fs 2395 which will ignore all the records with this size

- sucecssful domain name would have status code 200     
