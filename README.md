# Veebiarendus
## Linux Google Cloud Shell
Enne kasutamist käsud:
- updates: sudo apt-get update && sudo apt-get upgrade
- sudo apt-get install netcat-openbsd tcpdump traceroute mtr
## harjutus 1
sisesta ping -c3 8.8.8.8 
ja output: 3 packets transmitted, 3 received, 0% packet 
Järeldus: Arvutil on interneti ühendus ning interneti teenuse pakkuja teab, kuidas suunata edasi serveri 8.8.8.8 juurde.
## Ping
Selle saadetud sõnumi - echo request, võtab vastu sihtsüsteemi operatsioonisüsteem. Rakendusprotokollis (HTTP või SHH) on serveriprogramm, mis koostab vastuse ja saadab selle tagasi. Pingiga pole pingiserverit.
## Printf and netcat
- Printf on käsk stringide printimiseks. Prindib välja, mis sinna on pandud 
- Netcat (nc), on tööriist Interneti-teenustega käsitsi rääkimiseks.
