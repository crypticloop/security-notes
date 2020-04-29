# Group Policy

## Overview
* Allows administrator centralised control over computers on the network
* Group policies created centrally in AD
    * Then downloaded to where they're needed
* Group policies can be applied to:
    * Computers
    * Users
    * ...other things?

## History

### Registry
* Windows can be configured with registry
* Changes here are permanent
* Registry can change between OS versions
    * Compatibility issues after upgrading

### Group Policy is better because
* Changes to group policy not permanent
    * Can be rolled back
    * Administrator just unconfigures group policy
* Group policies are supported across versions
    * Might need to add some settings for compatibility with new OS

## Mechanics
* Group policy is client driven
    * Settings configured on clients by Client Side Extensions (CSEs)
* Newer operating systems have 4 CSEs
    * Older versions come with 3
    * Can add 4th with manual download
* Group Policy settings saved on DCs and replicated
* Client downloads relevant Group Policies
    * Processes them using CSEs
    * Settings which cannot be processed with by CSE will be ignored
