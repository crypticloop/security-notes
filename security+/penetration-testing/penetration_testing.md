# Penetration Testing

## Exam Reqiurements
* Identify and understand concepts

## Definition
* Act of measuring security posture
* Normally using assesment from outside agency
* Testers conduct attacks against organisation to help identify security weaknesses

## Penetration Tests vs Vulnerability Assesments
* Vulnerability assessment only identify existing vulnerabilities
* Pen testing does this, but also:
    * Identifies the extent of penetration an attacker could gain if vulnerabilities were exploited
* Pen testing delivers view on overall security posture

## Scope
* Scope is set of target outcomes for the penetration test
* Must be defined in the contract
* Can limit attacks to:
    * Certain methods
    * Certain parts of networks

## Steps of Penetration Tests
* Steps of penetration test modelled on process of an actual attacker
* Influenced by mixture of:
    * Killchain
    * Attack framework tactics

### Reconnaissance
* Allows tester understanding of target:
    * Network
    * General security posture
* Two types of reconnaissance:
    * Active
        * E.g. sending packets to endpoints
        * Detectable by defenders
        * Therefore not widely/often used
    * Passive
        * E.g. sniffing traffic, linked in connections
        * Encompasses most activity outside of target network itself
* Tools used can be classed as active/passive depending on their function

### Initial Exploitation
* Two purposes:
    * Demonstrate depth of vulnerability i.e. risk level
    * Demonstrate mechanisms involved in the attack vector

### Pivoting and Privilege Escalation
* This step demonstrates depth of intrusion/access/impact this vulnerability allows
* Demonstrates that these actions can be done undetected

### Persistence
* Establish some sort of persistence in network, including:
    * Creating backdoor
    * Setting up periodic exfiltration

## Types of Pen Testing
### Black Box
* Tester has very little knowledge of system/network
* Must discover vulnerabilities/network features during the test

### White box
* Tester has in-depth knowledge of system/network
* These types tend to be focused on testing specific features, e.g:
    * New functionality
    * Recent changes
* Two stage process:
    * Test before the change for baseline
    * Test after the change to detect improvement/new vulnerabilities

### Gray box
* Tester has some knowledge of system
* Efficiency benefits:
    * Testers don't waste time on test cases where they know they wouldn't make any progress
    * Don't have specific enough knowledge to know exact exploit to use
* 'Some knowledge' can manifest itself as experience with systems similar to target system