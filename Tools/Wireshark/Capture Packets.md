# Wireshark - Capture Packets

## Task 1
### Install and set up a stable version of wireshark in ubunt using apt

> sudo add-apt-repository ppa:wireshark-dev/stable

### Add the user to the wireshark group  to add packet capture capabilities

> sudo usermod -aG wireshark $USER

## Task 2
### Start a packet capture on an ethernet port and save it to a file
- the wired interface includes ethernet packet capture, - begins with "en" in wireshark
- wireshark app includes - start pkt capture, stop capture, save pkts to a file, load the capture file
- capture can be saved on the capture has stopped

## Task 3
### Use a display filer to detect HTTPS packts
> tcp.port==443


## Task 4
### Visit a web and detect its ip address using a display filter
- tls handshake display fileter can be used to detect a website visit in a pkt list : tls.handshake.type==1
- ip address is used in filter to obtain pkt info for a particular website: ip.addr==123.33.33.33

## Task 5
### locate all HTTPS pkts from a capture not contaning a certain ip address
- conditional stmt   used to include and eliminate pkts from a wireshakr capture
> !(ip.addr==9.43.33.33) and tcp.port==443

- a compound conditional should inlcude parentheses to avoid order of execution errors
> !(ip.addr=33.333.33.33) and (tcp.port==80 or tcp.port==443)


> sudo apt install wireshark
> sudo usermod -aG wireshark $USER   (-aG append a group)
> ip.addr
> tls.handshake.type==1
> tcp.port==443
> stop cature before saving the packet capture
