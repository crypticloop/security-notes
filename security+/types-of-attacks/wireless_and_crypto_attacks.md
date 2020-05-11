# Wireless and Cryptographic Attacks

## Wireless Attacks
### Replay Attack
* Easier with wireless as traffic easier to capture

#### Initialisation Vector (IV)
* Attacker steals initialisation vector
    * Might change slightly if sequential order detected
* Then carries out replay attack

* Attacker sets up own wireless access point
### Evil Twin and Rogue AP
* Proxies the internet to people signing up
    * Executing MITM attack in process

### Brute Force WPS
* WPS (Wifi Protected Setup) is protocol to secure wifi connection
* Uses 8 digit pin to secure connections
* Attackers can brute force this pin
    * Then use access to try and acquire WPA passphrase

### Bluejacking
#### Bluetooth Attacks
* Attacker sends unwanted messages via bluetooth
    * Sometimes making it appear as if messages are coming from known devices
* Manipulates target device with commands via bluetooth

#### Bluesnarfing
* Atacker connects to target device via bluetooth
* Uses bluetooth to download information

### RFID Copying
#### RFID Attacks
* Copying RFID signature from card etc.
* Then cloning onto transmitter to grant entry

#### RFID Denial
* Manipulating RFID reader to not react correctly to cards etc.
* Can use to deny entry

### NFC
* Attacks exploiting NFC such as that used in contactless payments
* NFC technology has direct access to financial institution
    * Therefore processes using these technologies need to be properly protected

### Dissasociation
* Attacker forces target device to disconnect from wireless network
* Then sniffs traffic of reauthentication requests
* Can then use these in replay attacks etc

## Cryptographic Attacks
### Birthday Attack
* Exploits possibilities of shared passwords

### Known Plaintext/Ciphertext
* Attacker manages to determine fragment of plaintext corresponding to ciphertext
* Uses this information to reverse engineer encryption
* Many current encryption algorithms protect against this

### Poor Password Choices
* Narrows spectrum of possibilities of possible passwords
* Reduces time taken for brute force attack

### Rainbow Table
* Rainbow table stores hashes and corresponding plaintext
* Attackers acquire hashes and use lookup table for plaintext password
* Defence: salt stored hashes
    * Adds characters to hash to make them longer

### Dictionary Attack
* Attacker attempts brute force with list of well known words
    * I.e. from dictionary
* Might make subsititutions
    * E.g. 'a' replaced with '@'

### Brute Force
* Attempting every possible combination of passwords

#### Online Brute Force
* Attacks tried against live authenitcation server
* Defence: Lock out auth attempts after number of failed tries

#### Offline Brute Force
* Attacker has managed to locally clone authentication store
    * E.g. Might have local list of password hashes
* Can now attempt authentication unlimited 
* Not limited by network latency
* Defence: Encrypt authentication database

### Hybrid
* Combination of all above password cracking techniques

### Collision
* Attacker exploits two inputs yielding same hash output
* Can alter contents of a file without integrity checks noticing

### Downgrade
* TLS technologies are permissably downgraded in certain cases to support backwards compatibility
* Attacker exploits reduced securuty of downgraded environment

### Password Replay
* Same as pass the hash attack
* Attacker sniffs traffic for password hash
    * Then passes this to authentication server to authenticate as target user

### Weak Implementation
* Attacker exploits weak cryptographic technology