# Veebiarendus
## Linux Google Cloud Shell
Enne kasutamist käsud:
- updates: sudo apt-get update && sudo apt-get upgrade
- sudo apt-get install netcat-openbsd tcpdump traceroute mtr
## harjutus 
sisesta ping -c3 8.8.8.8 
ja output: 3 packets transmitted, 3 received, 0% packet 
Järeldus: Arvutil on interneti ühendus ning interneti teenuse pakkuja teab, kuidas suunata edasi serveri 8.8.8.8 juurde.
## Ping
Selle saadetud sõnumi - echo request, võtab vastu sihtsüsteemi operatsioonisüsteem. Rakendusprotokollis (HTTP või SHH) on serveriprogramm, mis koostab vastuse ja saadab selle tagasi. Pingiga pole pingiserverit.
nt et näha host serverit ping yahoo.com (Ctrl+C et lõpetada)
## Printf and netcat
- Printf on käsk stringide printimiseks. Prindib välja, mis sinna on pandud 
- Netcat (nc), on tööriist Interneti-teenustega käsitsi rääkimiseks, erinevate serveritega ühenduse loomiseks või isegi serverina tegutsemiseks.
## harjutus 
Millist Web Serverit kasutab Google
printf 'HEAD / HTTP/1.1\r\nHost: www.google.com\r\n\r\n' | nc www.google.com 80
Vastus: Server gws
## Porti kuulamine 
Porti kuulamine on serveriks olemine. Programm, mis kuulab TCP-porti, ootab, et teine programm selle pordiga ühenduse loob. Kui see juhtub, saavad kaks prgrammi andmeid edasi-tagasi saata.
## Pordi numbrid
Pordinumbrid eristavad erinevaid rakendusi ja seansse samal hostil
Tava kasutaja saab kuulata 1024 kuni 65535.
juurjuurdepääsu nt sudo, siis kuni 1-ni portidel.
## Harjutus
Kahe SSH-terminaliga, ühes neist porti kuulav nc-protsess. Porti number 4356. Ja teises terminalis nc localhost 3456.
Näiteks, porti 3456 kuulamiseks: nc -l 3456 
Ühnduse saab lõpetda Control-D käsklus ja 1 nc väljub. Teine nc väljub, kui esimene sellest lahti ühendab.
## Sisu päringud
Enamik nc abil on saadud HEAD-päringud. HEAD  palub serveril saata ainult päised, mitte saata täielikke andmeid. 
Saab teha ka GET-i taotlusi:
printf "GET / HTTP/1.1\r\nHost: www.example.com\r\n\r\n" | nc www.example.com 80
## DNS
Domeeni nime süsteem
Kui DNS läheb maha siis ei saa avada veebilehte. Samuti ka kaitsemehanismid HTTPle
Et leida informatsiooni DNS kohta, käsud:
- Host (host -t a google.com) kergesti loetav
- Dig, tehnilisem aga rohkem infot.
    ## Caching vahemälu
    Hajutatud kataloog, et üks DNS-server ei peaks teadma kõiki maailma kõigi nimede ja domeenide kirjeid.
    Vahemällu salvestatakse kõik seni, kuni see suudab õige vastusega naasta.
    Neil on ettenähtud aeg, nii on informatsioon värske
 ## Domeenid
Top domeenid on nt com, net, org, edu
Alamdomeenid (nt wwww.näide.com j- näide.com) 
domains.google.com (loo domeen)

     
