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
- files and directory monitoring - whenever new data is written
- scripted inputs - scripts to extract certain log data from different sources and ffed to splunk for analysis

Best practives:
- logs sources discovery
- security and access control - restrict access to splunk data inputs, utilize encr commiunication, and follow secutiry practices
- scalabilty and performance - log collection, volume, frequency, splunk infra

Log Search and analysis in Splunk:
- search - analyse - insights
- search, filter, analyse logs
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


### Splunk cpmpliance and reporting
- importance of regulatory compliance
- splunk for cpmpliance management
- log management and retensions
- cmpliance monitoring and auditing
- reporting and visualizations
- integrating with compliance frameworks


### Splunk for Threat hunting and investigation
- log analysis and correlation
- advanced analytics and ML
- visualizations and dashboards
- incident investigation and forensics
- threat intelligence integration
- collaboration and automation


### Splunk for security monitoring and alerting
- pre-emptive htreat detection, ongoing security monitoring, effective incident response
1. centralized log collection
2. real-time security monitoring
3. advanced threat detection
4. alerting and notifications
5. customizable dashboards and visualizations
6. incident response and workflow integration
7. compliance monitoring


### Splunk architecture - splunk enterprise

- data inputs
- add data
- indexes - search, spl, 
- search, reports, alerts
- forwarding and receiving

### Add data by uploading
- add data
- search using spl
- sorutce, type | table field1 field2 field3
- soruce, type | table *   -> presents data with extra colums
- SAVe it to a new dashboard
- source , type | stats count by status(field)   - returns two rows error 10, success 100
- - source , type, status=error | stats count by status(field) | table count    -  it will jjust return the result number
- click visualization and select charts
- - source , type, status=success | stats count by status(field) | table count    -  it will jjust return the result number
  - slect different color
 
- view dashboard
 
- we can customize all the save tiems in the dashboard

### deployment models
- deployment models
- data storage on disk
- licensing
- apps and add-ons

**deployment model**
- configuration files   -  .conf files
- /etc
- 1. cloud
  2. enterprise
- Splunk Data pipeline:
  - input - data consumption
  - parsing - data examination, analaysis and transfer, adds meta data
  - indexing - write data to disk
  - searching - user interacts wiht data
 
- physical componnet
  - universal forwarder
1. departmental deployment
   - single search header indexer
   - upto 10 fwders
   - appropriate for 10 users
  
2. Small enterprise deployment
   - a single search head
   - 2 to 3 indexers
   - 100 to 200 fwders
  
3. Distributed search head
   - deployer configures the search head
   - config bundle
  
4. large enterprise dpeloyment
   - deployert
   - master cluster node - indexers
   - boundless horizontal scale

### How splunk stores data
- adds data to index
- default index
- internal index
- event - single row of data, key value pair - splunk adds defalt fields to all events
- raw data to index
- spread out in different directory or buckets
- buckets:
  1. hot - $SPLUNK_HOME/var/lib/splunk/defaultdb/db/*
  2. warm
  3. cold
  4. frozen
  5. thawed - restored form archival
- retirement / archiving policy
- backup
- configure indexes
- partition index data


### splunk apps
- Apps -> aws in search --> splunk add on for AWS
- install it - give username and pwd
- open the app
- cna see the app in the home page left side also
- go to app
  - security, search, insights
  - various dashboards like IAM insights, s3-data event, user activities
- go to etc folder and check the configuration files came with this new app - etc/apps -> splunk_app_sws_security/dfault -> see the .conf files


**Licensing**
- settings -> system --> Licensing
- 500mb licencesd daily volume for trail users
- change license group
- upload purchased license

- splunk enterprise commerical end user licenses
  - amt of idnex per day / vCPU count
- splunk enterprise volume based license
  - all capabilities
  - single instalce acrsos several computers
  - license cannot be combined with infra based permission
  - forbids searches if licnest stack is les than 100gb or data
 
- splunk enterprise infra license
  - 


### getting data into splunk
- upload any csv file
- New seacrh
- ou can select the fields in the left side, so that it will be shown in each record (intereing fields, selected fields)


### Understanding forwarders












