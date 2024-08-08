# File Inclusion

- LFI - local file inclusion
- RFI - remote file inclusion
- directory traversal

- get.php?file=userCV
- google.com/search?q=tryhackme

### Path traversal
- directory traversal
- requeste file  can be found in /var/www/app/folder-name
- dot-dot-slash attack
- /etc/passwd
- boot.ini
- windows/win.ini


### Local file inclusion
- php functions - include, incluce_once, require, require_once
- http://webapp.thm/index.php?lang=EN.php  - en.php is stored in one location
- we can try this  too it there no input validation - http://webapp.thm/get.php?file=/etc/passwd
- 
