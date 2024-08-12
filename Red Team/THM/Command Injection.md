# Command Injection

- ;
- &
- &&
- whoami

1. blind command injection
2. verbose command injection

blind:
- ping
- sleep
- whoami
- ">" - redirection operator
- cat
- curl
- curl http://vulnerable.app/process.php%3Fsearch%3DThe%20Beatles%3B%20whoami

linux payload:
- whoami
- ls
- ping
- sleep
- nc - netcat


Windows payload:
- whoami
- dir
- ping
- timeout

**remediation**
- php - exec, passthru, system
- pattern="[0-9]"  - echo passthru("bin/ping -c 4 "$_GET["ping"].");

Input sanitization:
- specifying the formats
- removes special chars

bypaasing filters : using hexadecimal values
