# Other Network Components

## Wireless Access Points (WAPs)
### Definition
* Point of entry for radio-based signals into/out of network

### Authentication
* 802.11 access points use SSIDs as authentication function
* SSID is wireless network name
    * Passed in header of packets between the router and devices on wireless network
* Only people who know this SSID can connect
* Issues:
    * Sent over plaintext during handshake so can be sniffed and used by attacker in impersonation
    * WAPs can beacon SSID letting device know when it is in range of the WAP - attackers also then know the network exists
* Mitigations:
    * Renaming SSID
    * Disabling SSID broadcast - inconvenient and security through obscurity
* Communication over wireless networks can be secured by many different protocols (oldest to youngest):
    * WEP - encryption was vulnerable, insecure
    * WPA - used dynamically changing encryption called TKIP, still ended up being vulnerable, insecure
    * WPA2 - Applied AES on top of TKIP, secure but some backwards compatibility issues with devices from before 2006
        * Routers offer mixed WPA/WPA2 protocol to support this
        * If all devices used are modern, best to just used WPA2
    * WPA3 - Released 2018, very secure
    * WPS - Designed for ease of use, no password
        * Physical or software buttons pushed on router and device for device to join
        * Or device pin entered into router software

### Signal Strength
* Weak connections can drop data packets
* Two key factors in signal strength:
    * Power
    * Environment

### Band/Bandwidth
* Wifi operates at two different frequencies:
    * 2.4GHz - supported by 802.11b, g, n
    * 5GHz - supported by 802.11a, n, ac 
* Radio access points used to resolve conflicts for new environments

### Antenna Type and Placement
* Want to cover maximum area while only covering area intended
* Two common types:
    * Yagi - broadcasts in straight line, longer range but directional
    * Panel - broadcasts in all directions, but short range

### Fat vs Thin WAP
* Fat (thick) - Can operate standalone
* Thin - control-based, another centralised device manages settings
    * Good for larger wireless environments
    * Also good for load balancing devices connecting to network

## SIEM
### Definition
* Security Information and Event Management system
* Provides centralised store for security analysts to use
* Aims to:
    * Aggregate - collect from multiple sources
    * Store
    * Correlate

### Alerting and Triggers
* Key functionality - able to alert based on triggers

### Time Synchronisation
* Events all gathered in UTC
* Easier to see progression of events across locations

### Event Deduplication
* Reduces irrelevant data

### WORM
* Write once read many
* SIEM recieves incoming events and then reads them many times, comparing to each stored rule
* Allows efficiencies with large data sets

## DLP
### Definition
* Data Loss Prevention
* Technologies to detect and prevent unauthorised transfer of information
* Can inspect packets and detect patterns matching sensitive information

### Types
* USB blocking - not possible to transfer data via external drive
    * Some devices will allow, but based on conditions
* Email monitoring - attaches to email server and searches content of email and attachments
    * Unrealistic to switch of attachments, too useful
* Cloud-based product - Offered by many, growing trend

## NAC
### Definition
* Network Access Control
* Allows management of connections on case-by-case basis

### Forms
* Network Access Protection (NAP) - Controls connections at the host, Microsoft tool
* Network Admission Control (NAC) - Determines whether device can enter network, Cisco tool

### Disolvable vs. Permanent
* NAC system needs to be able to inspect hosts, mostly uses agents on host for this
* Two types
    * Permanent - agent remains on host indefinitely
    * Disolvable - temporary, only present for use, can be reissued

### Host Health Checks
* Can check host health
    * Patched?
    * Has antivirus installed?
* Sometimes host added to sandbox segment so it can be patched to spec before being added to network

### Agent vs. Agentless
* Agent-based solution - agents installed on hosts, awaits connection attempt
* Agentless - Code stored on network and deployed to run on host as connections are made

## Spam
### Definition
* Undesired, unsolicited bulk email
* Security issues as well as just being annoying
* Spam filters introduced - software to prevent spam entering email stream

### Spam filtering methods
* Blacklisting
* Content/keyword
* Trusted servers
* Delay-based
* Reverse DNS checks
* Callback verification
* Statistical
* Rule based
* Egress
* Hybrid - all of the above

## Bridge
* Connection between two or more seperate network segments
* Operates at OSI level 2
* Allows network segmentation, which is important to security as reduces attacker's ability to move laterally

## SSL/TLS Accelerators
* Throughput between web servers and internet
    * I.e. enabling visitors to site to use TLS efficiently
* Usually employed on busy sites

## SSL Decrpytors
* SSL data encrypted, so difficult to analysts to examine for suspicious activity
* Device decrypts traffic so that analysts can examine

## Media Gateway
* Translates Telecoms protocols to other network protocols
    * Allows smooth sending and recieving
* Usually part of switch or firewall

## Hardware Security Module
* Network device managing and storing encryption keys
* Allows key use while centrally managing and protecting them
* Also have throughput benefits
