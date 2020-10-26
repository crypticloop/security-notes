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
1. Web server owner goes to Issuing CA to request certificate
2. Registration authority checks out web server owner's credentials and approves them
3. Issuing CA sends certificate to web server
4. Web server is now subject
5. User browses to subject
6. Subject sends certificate to user
7. User is Relying Party (RP)
8. RP has relevant Root CA pre-installed in their software
9. Private key of Subject's certificate might be compromised
10. Subject would tell Issuing CA that certifcate should no longer be trusted
11. Issuing CA would then put certificate on Certificate Revocation List
12. RP would check, when browsing to subject, if certificate was valid against CRL
13. Checks this against Online Certificate Status Protocol (OCSP) responder where they look up details about certificate

### Chain Vaildation
1. RP browses to subject
2. Subject returns its own certificate, as well as any chained certificate
3. RP looks at IssuerDN of subject certificate
4. It is not RootCA, but is CA1
5. RP looks for certificate in chain whose SubjectDN is CA1
6. RP finds this certificate and sees that its IssuerDN is RootCA
7. RP sees that they received no other certificates as response to their request to Subject
8. So RP looks inside its own trust store and finds cert where SubjectDN is RootCA
9. RootCA is issued by itself
10. RP uses public key of RootCA to validate certificate of CA1 certificate
11. RP successfully validates CA1 certificate, now trusts CA1 certificate
12. RP uses public key of CA1 certificate to validate certificate of SubjectDN
13. RP successfully validates Subject certificate, now trusts Subject certificate
14. RP uses public key of Subject certificate to communicate with Subject