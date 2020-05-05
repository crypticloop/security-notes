# Technical Attacks

## DoS vs DDoS
* DoS - attacker aims to cut of access to system or features of system using known vulnerability
* DDoS - DoS attack of overloading system with traffic, employing multiple attack systems
    * Multiple attack systems sometimes known collectively as zombie network

## Man In The Middle (MITM)
* Capturing of traffic between two hosts

## Buffer Overflow
* Input buffer overwritten with more data than space is available
* Bits written outside allocated buffer can be used to execute malicious code
* Happens due to poorly validated input

## Injection
* Malicious code executed by entering it into an entry field of application
* Dangerous because allows execution at privilege level of application
* Happens due to poorly validated input

## Cross Site Scripting (XSS)
* Script executed through use of input field in web process
* Happens due to poorly validated input
* Three types of XSS:
    * Non persistent - Injected script executes once and passes back result, is not stored
    * Persistent - script stored on infrastructure, continues to report data to attacker
    * DOM-based - Script executed via DOM using Javascript
* These attacks allow:
    * Theft of authentication assets
    * Session highjacking
    * Content/setting modification


## Cross-Site Request Forgery (XSRF)
https://www.youtube.com/watch?v=vRBihr41JTo
* Attacker exploits locally stored authentication assets of a user of the target site
* Attacker infrastructure makes request to target site using authentication assets of some user of that target site who has then visited attacker site
    * E.g. attacker is attacking online bank
    * Some person logs onto this online bank and authenticates, storing assets in browser
    * Attacker lures some person to their site (completely unrelated content) and gets access to authentication assets
    * Attacker sends request to bank silently behind their site, using these assets, transferring money from the person's account to their own account (hardcoded into the request)

## Privilege Escalation
* Increasing privileges available to attacker

## Amplification
* OVerwhelming a host with huge bandwidth of data
* Can be done with various techniques i.e. pinging entire network and forging return address as target of DDoS

## DNS posioning
* DNS table of target host modified
* Traffic from target host redirected at attacker's will

## Domain hijacking
* Changing registration of domain name to redirect traffic to attacker's own infrastructure

## Man-in-the-Browser
* Malware sits on target host waiting for user to navigate to some site in the browser e.g. their bank
* When they reach that site, malware changes instructions user sends to the bank
    * E.g. changes recipient of payment to themselves

## Zero day
* Takes advantage of vulnerability which vendor is not aware of

## Replay attack
* Attacker captures user communication and replays it later
* Hopes to achieve same result as when user sent it in the first place

## Pass the hash
* Attacker grabs hash in transit between user and target site
* Then sends request to site using hash to try and authenticate as user

## Highjacking attacks

### Clickjacking
* Attacker places overlay on webpage to make user click on something which they didn't mean to
* Can use click events to:
    * Redirect to attacker's infrastructure
    * Trigger events

### Session Highjacking
* Attack gains access to established session

### URL Highjacking
* Forcing users to navigate to URL which they didn't intend to

### Typosquatting
* Attackers place their own infrastructure at URLs which are small variations of legitimate site urls, e.g.:
    * gooogle.com
    * rnicrosoft.com


## Driver manipulation
* Drivers generally less secure than OS
    * So easier method for attacker to get foothold on environment

### Shimming
* Inserting code between driver and OS
* Has legitimate purposes, but is also exploited by attackers

## Refactoring
* Changing code which doesn't change external behaviour of code
* Attackers can exploit these changes to create security vulnerabilities inside the code

## Spoofing
* Making traffic appear to be coming from somewhere other than its real source

### Mac spoofing
* Spoofing MAC address of the traffic

### IP spoofing
* Spoofing IP of traffic

### Smurf attack
* Amplification attack with packet 'From' address spoofed as target host in traffic sent to whole network
* Target host receives all responses as DDoS