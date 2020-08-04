# Incident Response Process

## Overview
* IR plan should be starting point when handling an incident
* Should incude info on:
	* Process itself (incl. flowchart if possible)
	* Contacts
		* IR team
		* IT
		* HR
		* PR
	* Escalation criteria (with critical decision processes)
	* Conference number
	* Legal and regulatory guidelines
* Could include:
	* Checklists
	* Documentation and tracking forms ready to be filled in
	* Incident-specific guidelines and playbooks

## Incident Response Process
* https://www.ncsc.gov.uk/collection/incident-management/cyber-incident-response-processes
* 3 key stages:
	* Prep
	* Core response
	* Close down

### Prep
* Two stages:
	* Triage
	* Escalate

#### Triage
* Want to understand **severity** and **type/category**

##### Severity
* Assessed against:
	* Availability
	* Confientiality
	* Integrity
* Could use a severity matrix to aid this decision

##### Type/Category
* Type can refer to method or style of attack e.g:
	* Malicious code
	* Phishing
	* Insider
* Can also create matrix to help categorisation

#### Escalate
* Triage (especially determining severity) will guide escalation
* Escalation points should be documented
	* Contact details considering OOH and OOO
* Ensure people being escalated to have authority to make big decisions

### Core response
* 4 steps:
	* Analyse
	* Contain/Mitigate
	* Remediate/Eradicate
	* Recover
* Make sure everything is tracked

#### Analyse
* Prioritise here, time is of the essence
* Want to understand enough to contain/mitigate
	* And ultimately remediate/eradicate

#### Contain/Mitigate
* Involves isolating systems, resetting accounts etc.
* Also non-technical stuff e.g. media handling
* Attacker may react to this stage
	* Think actions through **carefully**
	* Could be better to wait and analyse more


#### Remediate/Eradicate
* Aim to fully remove threat from system
	* Can be similar to/simultaneous with containment
* Must monitor that changes were successful

#### Recover
* Systems returned to BAU
* Final actions taken with legal, press etc.

### Close Down
* Learn from incident itself and the response
* Questions form the incident:
	* Are there detections which could have prevented this?
	* What tactical or strategic fixes could have prevented?
	* Would any information have been helpful which could have been gathered beforehand?
* Questions from response:
	* Was it successful?
	* What could have been handled better?
	* Was there any missing data during response which would have been helpful
* In general, were the right tools and people involved, and how was communication?

## Extra info

### Playbooks
* Specific processes for specific events
* Should aim to script at least first stages of response, including:
	* Who to contact
	* Information on triage
* More advanced playbooks can contain information for IR cycle


### Incident Management
* Collection of co-ordinating functions for the whole response process
* Involves
	* Tracking and documentation
	* Update meetings
	* Escalation to senior management
	* Ensuring appropriate communication
	* Ensuring full lifecycle covered