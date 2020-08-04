# Router and Switch Security

## Exam Requirements
* Understand installation
* Understand configuration

## Routers
### Definition
* Network management device
* Forwards packets between network segments
    * Based on packet destination and internal tables

### Access Control Lists
* Used to determine whether packet should be forwarded
    * Checks source against ACL
* Disadvantages:
    * ACL maintenance difficult
    * Efficiency penalty with scaling
* To minimise impact, only implement ACLs on boundaries
    * Allow all internal traffic

### Antispoofing
* Measures on routers to ensure DDoS attacks cannot originate internally
    * Checks source IP and drops if packets don't conform

## Switches
### Definition
* Network device connecting devices on single network
    * Uses packet switching
    * Forwards traffic to destination
* Switch limited to node-to-node communication inside a network

### Port Security on Switches
* Security control on switches
* Controls which devices can connect to which port on the switch
* Based on MAC addresses
* Three main types:
    * Static learning - MAC addresses assigned to port, useful when there is dedicated hardware
    * Dynamic learning - switch learn MAC addresses to use as they connect, useful for small number of machines
    * Sticky learning - Allows multiple devices per port, persisting these setting across reboots to prevent attacks through power cycling

### Layer 2 vs Layer 3
* Traditionally switches operate on Layer 2
    * Newer switches with some routing functionality means they can operate at layer 3

#### Loop Protection
* Disadvantage of Layer 2 - Could not protect against packets stuck in loops
* Two methods put in place:
    * Open Shortest Path First (OSPF) - Robust gateway, logical point-to-point topology
    * Spanning Tree Protocol (STP) - Trims connections not part of spanning tree

### MAC Filtering for Security
* Selective admission of packets based on MAC address whitelist
* Security benefit limited as MAC addresses can be spoofed
    * Especially in wireless network where MAC addresses broadcast in plaintext