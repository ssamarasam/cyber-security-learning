# Course Name: SIEM Splunk Hands on guide

### Overview:

SIEM soltutions -> SEM + SIM
- real-time monitoring
- threat detection
- incident response
- compliance management

Process:
- log collection - newt devices, security appliances, apps, servers
- log aggresgation and normalization
- real-time monitoring - rule based, behaviour based
- threat detection and alerting
- incident response and workflow - incident response, automation, case management
- compliance management - collecting, analyzing and reporting

Benefits:
- improved threat detection - anamolies,   indicators of compromise
- enhanced incident response - centralized platform, automated workflow, collaboration tools, documented procedures
- regulatrory compliance
- understanding operational efficiency

Log collection:
Splunk forwarders:
- small, secure agents - gather and send logs to Splunk Indexes frpom a variety of sources
- servers, network devices, apps,
Syslog collection:
- logs form firewalls, swiutches, routers
APIs and integration:
- from systems and applications
- cloud platforms
- databases
- security tools
- other 3rd party solutions

Data Input configuration:
- web interface
- files and directory monitoring
- scripted inputs

Best practives:
- logs sources discovery
- security and access control
- scalabilty and perf

Log Search and analysis in Splunk:
- SPL - Splunk Queiry language -
- splunk processing language - to searcha and analyze data
  - terms
  - phrases
  - patterns
 
- field extraction and custom field extraction
- search modifiers and operators - to refine the search
  - time range
  - logical operators
  - wild card chars
 
  Search and analysis technique:
  1. filtering and narrowing down dat - time range, host, src, event type
  2. aggregation and statistic - counts, average, sum, matrix
  3. correlation and time series analysis - find patterens, anamolies, trends

visualization and dashboards
- charts
- graphs
- interatcive dashboard

Alerting and automation
- alert configuration - conditon, search query, statitical function
- automated response actions - sending notifications, executing scripts, triggering response
