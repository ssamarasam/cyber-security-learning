# Networking Fundamentals course from Linkedin learning (Kevin Wallace)

## Fundamentals
- Network
- LAN
- PAN
- CAN
- MAN
- WAN
- Wireless

Benefits of networking
- resource sharing
- communication
- redundancy

Network Addresses:
- MAC - 48 bits (24 bits for vendor code OUI / remaining 24 bits device id)
- IP
  - ipv4 (32 bits, using subnet mask, can identify network porting and host portion
  - ipv6 (128 bits , using prefix length

Parts and pieces of network:
- NIC Network interface card
  - wired nic, wireless nic, extrenal nic
  - provides a circuitory required for a clinent/device to connect to a network ( it might have rj-45 connectors, LED to show the spped of 100 or 1000 by blinking)
- SWITCH (max address to port mapping)
  - multiple ports
  - receives data and direct the traffic to destined network device
  - before doing that, it uses MAC address table to identify the devices with their mac address when there is a communication which sends data to all devices and leads to flooding
  - after learning during floowing and responce back fromt he desitned device, it maps all the mac with itsright device
  - later all data flows thru destined devices only
- Router
  - router takes decison based on IP address. IP routing table
  - when the IP is not found it its list, it goes to all zeroes meaning it will routed to the rest of the world which is internet
  - otheriwse it directs it to the most specific route. the rout with the longest prefix
  - protocol data unit (data) - packets - layer 3
  - a router connects LAN network to the Internet
- Wireless access points
  - extends the internet coverage from wireless modem
  - single connection back to the wired network
  - roaming - when a device gets connected to another AP without losing its signal at a different or extended place is called roaming
- copper cable
  - twites to prevent electroo magnetic interference, otherwise wires will act as antenna and wil transmist unexpected data
  - prenum cable - to avoid fume leakage in VAC system 
  - foil wrapped 
  - rj-45 connector T568A T568B colo codes to set the wires which will be used rightly in the networks
    - 100baset, 1000baset (data at high rates, limitations)
    - the longer it is, data losses might occur
- fiber optic cable to prevnt electormagenetic interferenec rather than copper cables. lights reperesents the data
  - Single mode fiber SMF and MMF
  - two strands .. one to send data, other to receive data
  - SMF for long distance applications to avoid multi mode distruptions (data in differnt order)
 
Notes:
- ethernet laer 2
- data routed by routers later 3

OSI model:
- to understand how everything works in a network

- physical layer refers to the network cabling or radio waves from wirelss access points  names dat at layer-1  as Bits
- data link layer - concerned with physical addressing - forwarding decisions based on mac address by Switch -  ethernet swictes operate here to make directing decisions -  name data at layer-2 as Frames
- network layer - concerned with logical addressing - forwrding decisions based on IP addressing done by routers - routers operate here at the layer 3 of OSI model  - data at this layet is Packets
- transport layer - concerned with the logical connections
  - reliable - transmission information was recieved or unreliable wwhen we are nto sure about the successful transmission 
  - TCP and UDP protocol
  - TCP - tranmissison control protocol - considred as reliable transport protocol
  - UDP - user datagram protocol - unreliable
  - data here at layer 4 is called as Segments
- Session layer - establishing, monitoring and then tearing down the communication sessions between the hosts
  - like API calls
- presentation layer
  - how data is represented
  - encryption protocls live here
  - formatting details live here
- application layer
  - users interaction
  - user interactig the web - then HTTP protocol/https,
  - DNS server wehn we dono the IP address
  - DNS protocol lives at layer 7

Please Do Not Throw Sasuage Pizza Away
All People Seem To Need Data Processing


PDNT are called PDUs Protocol Data Units (Bits, Frames, Packets, Sessions)
Bacon Frying Produces Salvation

TCP/IP Model:
- combines layet 5 thru 7 as single model called application layer
- Application Layer
- Transport Layer
- Internet Layer
- Network Access Layer / Network Interface Layer / Link Layer ( Physical layer + Data Link layer)


Protocols:
- HTTP - TCP port 80 when communicating with traditional web serevers
- HTTPS - TCP port 443
- DNS - TCP or UDP Port 53
- NTP - Network Time Protocol - UDP Port 123
- DHCP - Dynamic host configuration protocol - UDP Port 67
  - automatically assign IP address to the Network devices


DHCP - Dynamic host configuration protocol
- dhcp server
- discover, offer, request, acknowledgement  DORA
- router with DHCP relay agent
- DHCP v6 server
  - stateful - dhcp v6 server will retun all the necesary details ipv6 address, prefix length and dns details
  - stateless - netw device gets the prefix(whats the network we are on) from router using NDP (neighbour discovery protocol- EUI 64)  , remaining details can be recieved from DHCP stateless server
 
DNS:
- when the IP od any webserver is needed, netw device gets the ip address from DHCP server and then it will communicate with DNS server for the destined ip adress
- when DNS server responds with ip, it then send packts to the web server it needs

NAT - Network Address Translation:
- the router translates a client deice's local IP into global IP address and sends packets to global web server
- and the mappsing are stored in routers mapping table using NAT
- when the router gets response from web server, it then checks the mappings and pass the request to the local ip address of the client
- similarly if multiple devices are sending packets, routercreates new global addreess for each client
- thats the limititaion NAT enabled router cannot acieve all time
- 

- to solve this, if PAT(Port Address Translation) is configured,it creates only one global address for all local clients, but additionally it will store the Source PORT Number for each client
- so the source prot number is the mapping for each client
- 



