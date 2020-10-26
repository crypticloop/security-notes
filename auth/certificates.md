# Certificates

## Overview
* Certificates prove **who you are**
* They rely on some sort of trusted root
* They can exist in chains

## Questions
* Does every certificate exist in conjunction with a public and private key?
* Why are some certificates signed with their own private key, while others are signed with someone else's?

## PKI Examples
### Simple Web Server
1. Web server owner goes to CA to request certificate
2. Registration authority checks out web server owner's credentials and approves them
3. CA sends certificate to web server
4. Web server is now subject
5. User browses to subject
6. Subject sends certificate to user
7. User is Relying Party (RP)
8. 