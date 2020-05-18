# Proxies and Load Balancers

## Proxies
### Definition
* Filters traffic between two points
* Provides anonymity as it sends traffic requests on behalf of end system behind it

### Types
#### Forward Proxy
* Proxy server takes requests and forwards them

#### Reverse Proxy
* Sits infront of public facing applications 
* Provides security by:
    * Filtering requests
    * TLS decryption
    * Load balancing

#### Transparent Proxy
* A.k.a tunneling proxy
* Redirects requests without modifying
* Maintains anonymity for end system

### Classifications
* Application - proxies for specific application
* Multipurupose - proxies for several things

### Functionalities
* Anonymisation
* Caching - local copies of common requests to reduce bandwidth usage in large organisations
* Content-filtering - often used in corporate environments
* Open - open, available to all
    * Can be used to circumvent content filtering
* Web proxy - Specialised caching for popular websites

## Load Balancer
### Definition
* Distributes load between different end servers
    * Often used for web servers and high bandwidth transfer systems
* Increases performance and fault tolerance
* Especially effective in stateless systems
    * Because multiple end server can process each request without prior knowledge of other requests

### Scheduling
* Decisiopn logic for load balancer routing
* Two main types:
    * Affinity-based - attempts to keep host connected to same resource throughout session
    * Round-robin - Cycles requests between resources, sometimes dependent on resource load

###  Schemes
* To avoid single point of failure, often have more than one load balancer
* Different schemes can be used to determin load balancer architecture:
    * Active-Passive - single load balancer does all work with secondary unused but can take over if primary fails
    * Active-Active - multiple loadbalancers share all traffic, often plus one inactive backup to subsitute in case of failure

### Virtual IPs
* IP address of target system won't match that on traffic being passed to router
* Load balancers expose themselves as virtual IP
    * Allows multiple systems to be reflected as single address
* F5 devices implement this