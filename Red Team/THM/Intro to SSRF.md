# SSRF

- vulnerability which allows malicious user to cause the webserver to make an additional or edited http request to the resource of the attacker's choosing
- 1. regular ssrf - retuns data to attackers screen
  2. blind ssrf - no info is returned to attackers screen

- &x=
- server=
- url=
- form=/contact/area/
- value="http://server.website/com
- blind ssrf: use external http looging tools: requestbin.com, own http server, burp-suite's collaborator client
- 
