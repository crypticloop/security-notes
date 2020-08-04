# IDS/IPS

## Exam Requirements
* Understand installation
* Understand configuration

## Definition
* Intrusion Detection System (IDS) detects and monitors suspicious activities
    * And alert security professionals
* IPS same as IDS with addition:
    * Can also stop this activity

## Location 
* Host-based (HIDS/HIPS)
    * Can only detect unauthroised host use
    * Benefit: increased granularity of monitoring
* Network-based (NIDS/NIPS)
    * Can detect unauthorised host and network use
    * Disadvantage: Can only asses network traffic

## Components of IDS
### Traffic Collector
* Allows tool to collect information
* Looks different for different types of IDS
    * HIDS - security / audit logs
    * NIDS - sniffer which writes to external database where data can be analysed

### Signature Database
* List of IOCs and identifying signatures
    * I.e. list of values which, if observed, indicate malicious activity
* Signatures can take different forms:
    * Hashes
    * IP addresses etc.

### Analysis Engine
* Service containing logic to compare traffic signature database

### UI and Reporting Tools
* UI usually web-based GUI
* UI used to configure:
    * Application logic
    * Reporting processes

## Categories of IDS/IPS
### Signature
* Matches detected traffic to known signatures
* Relies on blacklisting
* Two major weaknesses:
    * Definitions/signatures require constant maintenance to keep up with new IOCs
    * Scalability issues with large signature sets (lookup efficiency)

### Behavioural
* Judge activity based on behaviour
* Configured by providing **whitelist rules** describing permitted behaviour
* Disadvantage:
    * New behaviours are often introduced
    * Will create large number of false posiitives

### Heuristic
* In between signature-based and behavioural-based
* Uses AI to detect suspicious behaviour
    * Defines grey area where some activity is allowed
    * Define black area where activity definitely not allowed
* Professionals in charge of maintenance are expected to be able to tweak algorithms to fit use cases/new behaviour

### Anomaly
* Learns to block/detect on acitivty deviating from learned baseline

## NIDS/NIPS Methods
### Inline vs. Passive Sensors
* Inline: monitors in realtime on network device
    * Disadvantage: if it breaks, all traffic is blocked
* Passive: writes copy of observed traffic to data store
    * Disadvantage: no realtime blocking

### In-band vs. Out-of-band
* In-band: application of blocking based on inline sensing
    * Same realtime benefit vs. performance disadvantage trade off
    * Typically used in high value, low traffic environments
* Out-of-band: application of blocking based on passive sensing
    * Same low impact vs. reactionary trade off
    * Typically used in high traffic environments

## Other useful definitions
### Rules
* Logic for deciding whether traffic should be blocked/reported or allowed
* Can be simple (blacklist/whitelist) or complex (heuristic/anomaly based)

### Analytics
* Requirement for processing of large datasets which will be passed to SIEM
* Should be parsed to deliver only useful information

### False Positives
* Rule triggered on no meaningful event

### False Negative
* Meaningful event does not trigger rule
