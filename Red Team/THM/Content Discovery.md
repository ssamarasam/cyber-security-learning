
### robots.txt
robots.txt - allow/disallow

### favicon - framework
https://wiki.owasp.org/index.php/OWASP_favicon_database


> curl https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico
> uhfevboho84uty982798-gi

> curl https://static-labs.tryhackme.cloud/sites/favicon/ - UseBasicParsing -o favicon.ico
> Get-FileHash .\favicon.ico -Algorithm MD5

### sitemap.xml
- path that org wants to display - may contain secret path or old path


### HTTP headers
- software versions
- programming language/script language

> curl http/siteurl -v
> -v --> verbose
>

### Frameowrk stack
- get the framwork url
- find the admin page of framework of your target webpage


### OSINT - Google Hacking / Dorking
- site:   -- filter in google
- site:tryhackme.com admin   -> retun resuls which contain only admin
- inurl:admin
- filetype:pdf
- intitle:admin


### Wappalyzer
- online tool/browser extension
- identify what technologies  a website uses, framework, CMS, payment processors, version numbers

### Wayback machine
- historical archival of websites

### GIThub

###   S3 buckets
- storage service provided by AWS
- format : http(s)://{name}.s3.amazonaws.com
- can be discovered in many ways - finding url in the website's page source, github repos, or during automating the process - like using common terms "name-assets", name-www, name-public, name-private


### Automated discovery
- wordlists
  - passwords
  - directory, file names
  - https://github.com/danielmiessler/SecLists
 
  - Automation tools:
    - ffuf
    - dirb
    - gobuster
   
**ffuf**
- ffuf -w /usr/share/wordliss/SecLists/Discovery/Web-Content/common.txt -u http://10.10.0.37/FUZZ

**dirb**
- dirb http://10.10.0.37/FUZZ usr/share/wordliss/SecLists/Discovery/Web-Content/common.txt


**gobuster**
- gobuster dir --url http://10.10.0.37/FUZZ -w /usr/share/wordliss/SecLists/Discovery/Web-Content/common.txt

root@ip-10-10-239-108:~# gobuster dir --url http://10.10.0.37/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.10.0.37/
[+] Threads:        10
[+] Wordlist:       /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Timeout:        10s
===============================================================
2024/08/05 12:10:34 Starting gobuster
===============================================================
/assets (Status: 301)
/contact (Status: 200)
/customers (Status: 302)
/development.log (Status: 200)
/monthly (Status: 200)
/news (Status: 200)
/private (Status: 301)
/robots.txt (Status: 200)
/sitemap.xml (Status: 200)
===============================================================
2024/08/05 12:10:36 Finished
===============================================================



