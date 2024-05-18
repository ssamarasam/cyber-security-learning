
# General Security Concepts

Threat - anyting that could harm, loss, damage or compromise to IT systems
Risks
Vulnerability

Confidentiality
- encr
- access controls
- data masking - obscurng data inaccessibile (like hiding 12 digits oif card number)
- physical sec measures
- training awareness

> confidentiality -> encryption

Integrity:
- data accuracy
- trust
- system operability
1. hashing - hash digest /   digital footprint
2. digit sig - using users private key, ency and hash it
3. checksums - during transmit 
4. access controls
5. regular audits

> integrity -> hashing

Availability
- ensu business conti
- maintain cus trust
- upholding an org's reputation

**redundancy**
- server redudancy
- data redu
- netw redun - if one netw path fails, can travel thru other route
- power redun

> Availability -> redundancy

Non-repudiation - undeniable proof of their action
- digital signature - hashing the msg with digitally signed and encr the hash digest with the users private key using asymmetric encryption
1. confimring the authenticity of digital transactios
2. ensuring integrity
3. providng accountability

> Non repudiation-> Digital signature

Authentication:
mthods:
- something you know
- you are
- you have
- you do
- somwehere you are

why?
- prevent unauth access
- protectuser data and privacy
- ensure resource validity - valid/authenticated users only can use allowed resouces - network and cloud

factors
- knowledge factors
- location
- pocession
- inherence
- action


Authorization
- role based, rule based, attributes based controls to determine permissions
1. protect sensitive data
2. maintain system integ in org
3. create more streamined user exps

authorization - set of rules/policies - used to dictate what actions user can perform once verified

Accounting:
- a sec measure that ensures all user activities are prope tracked and recorded
- monitoring and logging the actions of users
- provides tranparency, security and acocuntability
- robust accounting system
  - audit trail
  - rgula compliance
  - forencis analys
  - reosrce optima
  - user accontability

  how?
  - syslog serves
  - siem
  - network anaysi tool

  Security control categories:
  1. technical controls - soft/ward tech tools to protect
  2. managerical controls - adminitrative controls - strategic planning and governance side of security
     - risk assessments
     - security policies
     - training pgms
     - incident response startegies
  3. operational controls - involves procesudes and meausers designed to toretct data on a day to day basis and govenrd by intrenal process and human actions
     - backup procedures
     - acocunt reviews
     - user training pgms
  4. physical controls
     - physical secu
     - survial camer
     - shredding of sens data
     - sec guards
     - lock doors

  security control types:
  1. preventative controls - firewall
  2.   deterrent controls - waring signs
  3.   detective controls - ids, seim
  4.   corrective controls - fixing sys, quqrentine malwares
  5.   compensative controls - lower secured or legacy os.. but with use of vpan, we can add security
  6.   directive controls - pocicies
 
  Gap analysis:
  - current and desired performamnce
  - 1. scope of analys
    2. gather data on current state of org
    3. analyze data toidentify gaps
    4. develop a plan to bridge the gap

  1. technical gap analysis
  2. business gap analysi - business process wher they feel shoft compared to desired plan

 priotitize gaps
 
  plan of action and milestone - POA&M
  - outlines the spci meausre to address vul
  - alloca resos
  - set up timelines fo each remediation task

Zero trust:
1. control plane - identty and who gets access and how
   - adaptive identity - udneatnd user behavio, loca, activ
   - threat scope reduction - limit user acces, limit attck surface
   - policy driven access control - devlop, amange, enfore plocies , rules
   - secure zones - isolated env with a netw to house sens data
2. data plane - ensures that policies and rpocedurs are properly executed
   - subkect /system
   - policy engine
   - policy admin
   - policy enforment point


### Threat actors

Motivation:
- data exfiltration
- blackmail
- espionage
- war
- philosophical or political beliefs
- service disruption
- financial gain
- ethical reasons
- revenge
- disruption or chaos

Threat actor attributes
based on - origin 
- internal or extrenal
- resources or funding
- level of sophistification and capability
  - low - lowest skilled - script kiddies
  - high -


unskilled attackers
- taget small companies
- initiate DDoD attacks
- opportunistic
- tool - use tools like low orbit ion cannon
- lacks tech knowledge to craete or modify malwares
- gaining recog or for thrill
note: APT - advanced persistant threatds


hacktivists:
- indi/grps use their tech knowlege to promota  cause ror dive social chane instead for personal gain
- techiniques:
  - web defacement - electorinic graffiti - actr of vandalism
  - ddos - verwhelming a web to cause service disruption
  - doxing - public release of private info of an indi or an org
  - leak of snstive data
  - ananumus
  - lulsec - 50 days of lulz
 
Organized crime:
- sophisticated / well structred enti levegares resos and etch skills for ilicit gain
- use:
  - custom malware
  - ransomware
  - sophisticated phshing campaings
  - exploit emerging tech like - crupto, dark web, celluar collection devices
  - engage in variory o ililict activities like
    - data breaches
    - identify threft
    - ransomware attacks
    - online fraud
  - for financial gains but can be hired by anyone - fin7, carbanok
 
Nation-state actors:
- govt sponsored but kept a s seperate entity so that govt can deny their involment
- false flag attack - attack orchestrated in a way that it appears to originate from differnt source or group
- techniuqs
  - creating custom malware
  - using zero day exploits
  - becoming an advanced persistant threat
  - (nation state ctor - APT due to their long term persistance and stealth)
  > APT - prolonged and targeted cyber attack - in which inrtuder gets unathu access and remains undetected  for an extended period of time - trying to steal data or monitor netw activities rather than cuase immedite damage
  - why they attack?
    - gather inteligence
    - disrupting critical infra
    - inflicining political process
  - they also do cyber esponinage to steal intellectual property or gain competive advantage in competteive industries
  e.g: stucknet worm
   - malw used to sabotage iranians nuc pgm
 
insider threats 
- internal emp , contarctor , or anyoen who has access and knowleg about itrenal infra
- extensive access - like admin
- insiedr attacj forms
  - data theft
  - sabotage
  - misuse of access privileges
- motivations?
  - financial gain
  - revenge
  - carelessness / lack of cyber sec awareness/best rpatices like newbie
eg. snowden, twiietr attack of 2020

Shadow IT:
- the use of IT sys, device, apps, svs with the excilt org approval (stealth it, clinet it, shadow it)
- shadow it:
  - use of perosnl devices fo waork purposes
  - installation of unapproved softw
  - use of cloud servi not pporv by org

eg:
- usb
- ext hdd
- keyboard
- wired mouse
- netw adapter


They may bring wide range of vulnerabilities as thier life cycl is not managed by an org

potenal data breaches, non compliance with regu and sys disrp

- plusgins
- extension
- byod

- use of google drive, dropbox without the knowlge of org is also shadow IT - can lead to data leakage oif not properly managed

Threact vectors and attack surfaces:

Threact vector:
- the means or pathway by which an attacjer can gain unauth access to netw, compu to deliver mali payload or carry out an unwanted action

Attack surace:
- encompasses all various  ponts wher an unauth user can enter data or extract data from an env
- sum of all vuls and entry pooints and attacker could exploit


threat vector as how of an attack
attack surface is the aware of the attack

if atack surce is netw, to sigificant imcrease sec posture of netw
- restict access
- removing unne soft
- disabling unsued protocols

Threat vectros in enterprises:
- messages
- images : stegno attack - embeding mali code within pixels
- files
- voice calls
- removable devices - baiting - leaving usb with mali code
- unsecure netws
  - wireless - evil twins - mimic the legitimate wireless access points
  - wired - mac address cloing, VLAN hopping
  - bluetooth - blueBorne(vul attack pspread malware, on path communi to intercept communi), blueSmack( a type of ddos attack, crash dev and make inoperable)

threat vector - means or pathway by which an attacker can gain unautorized access to a computer or a network to deliver a maicious payload  or carrty out an wunwanetd action
attack surface - excompasses on al th various points where an attacker can enter data or extract data from an env

Outsmart threat actors:

TTPS - tactics, techniques and procedures
deception and disruptive techniques - to undertand the TTPS of an attack by attackers
- deisgned to mislead, consife, divert attackers fromc ritical assesta while similtaneoly detecting and neutralizeing threats

1. honeypots
   - decoy sys - allow accatakers to understand attackers' methods, motives and TTPs
   - can be used against insider threats to detech internal fraud, snooping and malpractice
   - emulation app to simulate actival netw or application
   - designed to log all inetraction/ transaction to provide values insigtes to the threat landscape
   - instal in screened subnet or osilated segment - easyf or attackers
3. honeynets - grp of honeypots to mimic an entire netw including orters, swicthes and other new devices - but can end up a s dowside sward since an attacker can learn the how the newt architure is made in the org
4. honeyfiles
   - decoy file placed with a syste m to lure  in potential attackers
   - shoud, apprea contain valueable information to make attacker to go aftr the data
   - set us a s trap - IDS inform sec team and some file whic have embedded code allows them to enumurae the attackers network once the file is open
   - unique embedded file to help track the file if it is stolen or copied
6. honeytokens
   - peice of data or resource with no legitimate data to use but can be monitored for access or use
   - fake user accout, url, a dummy database record,
   - if honeytoken is used or access - clear indication of potential security breach is likely occuring
   - particulatrly sueful fodetcing insider threats
   - any inetarction with them is suspicous
  
Other techniques in decpeion/distrptiv tech:
- using bogus dns entries
- creaing decoy directories
- generating dynamic pages  to stop web scraling
- using port triggering - to hide services
- spoofing fake telemtry data - during adetcted netw scan


### Physical Security
Fencing - prevent people
Bollards  - prevent vehicles

Attacking physical security with brute force:
- forcible entry - breaking
- tampering with sec devices - tamper deives - soltion: reduct device at multiple places
- confronting sec professional - 
- ramming a barrier with vehicle

Surveillance systems
- a security perosnall or sensors and cameras
- 1. video
     - motion detection
     - night vision
     - facial recog
     - remote access thru smartphone/computer
    wired/wireless
    CCTV:
    - indoor/outdoor
    - Pan Tilt Zoom PTZ - can aletr the direction of camera
    where?
    - data center
    - telemcoom closets
    - entrance or exit
   shoudl be acapable of identifiying intrustion using ML
  
  3. sec guards
  4. lighting
  5. sensors
     1. infrared - low light, heat identyfy human animal 
     2. microwave - detetc movemts emiting microwave pulses and meausringt he ferlction of moving objects - large ares - sometimes prone to be false alarms
     3. pressure - activate whn a specief amt of weight is detected on the sensor that is embetted on a mat or floor - identy unauth entries in spec areas and alert owners
     4. ultrasonic sensors - meause the refle of ultrso waves of movig objects - aumtomated doors or detectmovement in indoor env
    

Bypasing surveillance systems
1. visual obstruction - paint ballon on camera
2. blidng sensors and cameras - hig h power falsh light, heating up room to damage infrared sens
3. acoustic interferarance - loud noise, music
4. elctro magtnei interfe - EMI generatros, jammers to distupt the radio frequencies
5. physicl env attack

sotuoion:
- tamper alrms
- backup powe ups
- encr frequencies


Access control vetibue 
- two door system - elctronically controlled - only one door can be opend at a given time
- opens the second door when the first door is open
- autheic, identy, access
- prevents piggy backing, tailgating
- RFID id cards - radio frequency identification
- NFC - near field communication
- magnetic strips - legacy (like back on the credit card)
- action is logged
- access based on role
- audit trail to log user actions
- sec guard at access contro, vesibule as visual detrrent and also to reponse immediate concenrs
  - visual asistan
  - assitance
  - check identity
  - response

Door Locks:
- pad locks with key
- pin locks
- wireless locks  using nfc
- biometric
  - false accecptance rate
  - false rejection
  - equal erorr rate ERR
    - calle as  croosver error rate CER - meaure effectiveness of a biometric system
  - MFA
- cipher lock - mechanical locking systems uses push buttons, often numberrd and requris the correct combination to be entered for access

Access Badge Cloning:
- vulnerability of able to clone access badges to bypass your authentication systems
- copy of data from an RFID or NFC card to another card or device
- 1. scanning
  2. data extraction
  3. writing to a new card
  4. using cloned access badge

hw to prevent?
1. implement advaced encr in card based authen systems
2. MFA
3. regularly updated securty protocols
4. educate the users
5. implement the use of shielded wallets or sleeves wih rfid access badges
6. monitor and audit the access logs


### Social Engineering
- the art of exploiting human psychology to gain unautho acesss to systems, data or physical spaces

Motivational triggers used by scial engineers:
- social engineers use these below factors to gain trust or achive their intended action
1. authority
2. urgency
3. social proof - if soemthing isused by many or if some page is liked by many and friends, we think thats legitimate  - psychological phenomenon - if a social engg forces one guy to post something, hten it goes to another to anther a slegitimate one by one - e.g signing up a course which has 100,000 reviews and likes of it
4. scarcity - psychological pressure when they belive a prod is limited or in short supply , poeple act quickly 
5. likablity - associate with being nice, friendly, socially accepted by others
   - sexual attraction
   - pretending to be a friend
   - common interest
7. fear - a great motivator like ransomware. if you dont do what i tell you, then this wll happen (Fear and authority)

Impersonation: as a social engg attack
1. impersonation
   - adversary assumes the identity of another person to gain unautho access
   - attacker might intimidate as other and gain trust
   - 1. unautho acess
     2. disruption of serv
     3. complete sytem takeover
2. Brand impersonation
   - attacker pretends to represent  a legitimate company or brand
   - attacker may use brnad logos, legitimate kind of emails, web pages, online rpesence to make people believe whom they clim to be
3. Typosquatting
   - attacker registers a domain name similar to popular wbe site but contain typograhical errors
   - url hijaking or cyber-squatting
   - user who mispell urls and it might lead to mali websites and become victorms of their typosquatting
   - companies may register original url and also mispelled url to protect users
4. watering hole attack
   - an attacker attacks a commonly used website or service and then wait for users to use those attacked services to capture those user's details
   - like animals wait near water source for their prey to come and drink water and then attacks the animals
   - to prevent these, orgs must keep their systems up to date
  

Pretexing:
- is way to give some amount of information that seems true so you will give us more information to fill in the gaps

Phising attacks:
1. phishing
   - email represnting a legitimate personal to gain trust, or to click mali link, or to download mali attachment
   - sent to mass group of individuals
   - spray and prey
3. vishing
   - voice phishing
   - betetr approach than email phsing.. ike a abnk repres call
5. smishing
   - SMS phishing
   - link via sms, urgency
7. whaling
   - a form of spear phishing targetting high profile individuals CEOs CFOs - 
8. spear phishing
   - targetted form of phishing - specific grp of individuals or orgs - attackers gather info and send personalized emails - higher level of customization - higher success rate
   - target users
9. business email compromise
   - if attacker compromises one email acocunt, then use that account to affect otehr email acocunts or making employees to do their inted action using the trust of compromised account

preventting phishing attacks:
- anti phishing campaigns - trainings to eployees
  - generic greetings
  - spelling and grammer mistakes
  - spoofed email addresses

  comonly used key indicators:
  - urgency
  - unsual reqs
  - mismatched URLs
    - word based email
    - html based email show display text and hides url. hover on it to see real url address
  - strange email addresses
    - display email address
    - real email address by cliking it
  - poor spelling and grammar


techniques:
- conduct trainig
- recog phsing attempts
- report suspicious messages

Conducting an anti-phishing campaign:
- free program - Trend Micro : phish insights

Frauds and Scams:
fraud:
- the worngful or criminal depction to steal infor from user

Identity fraud:
- the use of another persons's PI without authorization to commit a crime ro to decive












