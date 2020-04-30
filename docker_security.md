# Docker Security

## Overview
* Containers are inherently secure - shield processes inside the container from the host
* Need to monitor them to ensure they aren't used maliciously

## Events to monitor
* Good overview of Docker security considerations: https://blog.aquasec.com/docker-security-best-practices

### Interactive changes to files in known mapped volumes
* Monitoring the configuration files for ad-hoc changes which might:
    * Add volumes
    * Expose ports
* Only relevant if these are only meant to be configured in Git/some SCM tool

### Any volume to high level directory on host
* Volume created to `/` is very unlikely to have use that isn't either malicious, or insecurely configured
* Monitor for any containers which are run with this or similar high level directory volume mapping

### Any interactive changes to running containers
* Source: https://docs.docker.com/engine/security/security/#docker-daemon-attack-surface
* Someone shouldn't really be able to change attributes of the container while it's running
    * Adding volumes
    * Exposing ports
* Could extend this to a container being stopped and started again
* Example of exploiting fs mounts: https://blog.aquasec.com/threat-alert-docker-api-host-takeover

### Any interactive login
* If someone execs into a container, they have unrestricted access to any files in attached volumes
* They may be able to access content that they are not permissioned to see, so this should be alerted on
    * However this might lead to a load of false positives
* Could still write all of these events into an index, and from there additional filters can be added for alerts

### Changing bridge network
* Source: https://stackoverflow.com/questions/54720587/how-to-change-the-network-of-a-running-docker-container
* Some networking can be done using bridges **(needs more research)**
* These can be changed on the a running container
* Attacker could use this to expose another point of entry into the container e.g. an SSH port mapped to a random port on the host
* Therefore, should be monitored

## Reports
* Crowdstrike: https://www.crowdstrike.com/wp-content/uploads/2020/04/container-security-solution-brief.pdf



