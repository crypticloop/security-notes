# Firewalls

## Exam Requirements
* Understand:
    * Installation
    * Configuration

## Definition
* Can be hardware-software based
* Monitors and controls data into/out off a network segment
* Makes decisions on whether to allow or block traffic based on configuration

## Mechanism
* Security policies enforced through
    * Network Address Translation
    * Basic packet filtering
    * Stateful packet filtering
    * ACLs
    * Application layer proxies

### Network Address Translation
* Designed to address IPv4 limitation
    * Security came as a byproduct
* Entire network is displayed as single public-facing IP
    * So end user never learns IP address of individual host inside network
* Firewalls can be configured to perform this

### Basic Packet Filtering
* Firewall examines packet header
* Then filters based on rules using:
    * Ports
    * Protocols
    * Source
    * Destination
* Rules can be very specific
    * E.g. only block particular ports on some subset of hosts behind firewall
* Efficient, but filtering capability limited just to information contained in headers

### ACLs
* Usually used in file systems
* Can also be applied to firewalls
    * Permits based on idenities/other features of traffic
* Also read top-down, so implicit deny should be at bottom

### Application Layer Proxies
* A.k.a Application-based firewalls
* Can perform in-depth analysis of packets sent to it and decide on filtering accordingly
* However performance is very slow
    * Should only be used where deep inspecition is required
    * I.e. to mitigate risk on application where PII is stored

### Stateful Packet Inspection
* Works alongside basic packet filtering
* Filtering mechanism encorporating knowledge of previously processed packets i.e. stateful
* Examines additional properties e.g:
    * New connection vs. existing connection
    * Send vs. acknowledge
    * Originating interally vs. originating externally
* Can also use these firewalls to keep ports closed until needed
    * Prevents attackers from port-scanning

## Rules
* Firewall rules determine criteria for traffic to be allowed or dropped
* Should be initiated with **implicit deny**
    * Any permitted traffic needs to be explicitly specified
* Rules are read top-down, so implicit deny should be **at bottom**

