

# eszközök

router: 

- cisco isr 4451 

- 2 db



switch: 

- Cisco CBS350-24T-4G-EU Managed 24-port GE, 4x1G SFP 

- 14 db



access point:

- cisco business 150 ax

- 6 db



server:

- DELL PowerEdge R730 (16xSFF)

- 2 db



számítógép:

- DELL OPTIPLEX TOWER

- 194 db



### router

#### első router :

Alapkonfiguráció:
- megkapja az R1 nevet
- megkapta a 192.168.99.1-es ip címet

HSRP:

- vlanonként standby 

- Virtuális IP vlanonként változik pl vlan 28-nál :192.168.28.1

- Teljes redundancia elérése

- B épületben 1 kapcsolat az ISP-hez a giga 0-ás porton

SSH:

- minden hálózati eszközön SSH használata

- második verziót állítottunk be az SSHnál

- domain névnek a trefort.hu

- felhasználónév amin el lehet érni: admin

- leszó hozzá: admin

- 2048 bites titkosított kulcsott generáltunk

- telnetett letiltottuk a nagyobb biztonság érdekébben

Routing:

- a giga 0-ás porton csatlakozik fel mind két router az ISP-re. Erre megadtuk a kért statikus routingot ami keresei a 0.0.0.0 0.0.0.0 hálózatot

Vlan + HSRP:
- priority: 150

- preempt van beállítva

- Native vlannak a vlan 100 van beállítva.

- ha a router meghal akkor a második router fogja átvenni a szolgálatot.

#### második router :


Alapkonfiguráció:
- megkapja az R2 nevet
- megkapta a 192.168.99.2-es ip címet

HSRP:

- vlanonként standby 

- Virtuális IP vlanonként változik pl vlan 28-nál :192.168.28.1

- Teljes rendundancia elérése

- B épületben 1 kapcsolat az ISP-hez a giga 0-ás porton

SSH:

- minden hálózati eszközön SSH használata

- második verziót állítottunk be az SSHnál

- domain névnek a trefort.hu

- felhasználónév amin el lehet érni: admin

- leszó hozzá: admin

- 2048 bites titkosított kulcsott generáltunk

- telnetett letiltottuk a nagyobb biztonság érdekébben

Routing:

- a giga 0-ás porton csatlakozik fel mind két router az ISP-re. Erre megadtuk a kért statikus routingot ami keresei a 0.0.0.0 0.0.0.0 hálózatot

Vlan + HSRP:
- priority: 150

- preempt van beállítva

- Native vlannak a vlan 100 van beállítva.

- ha a router meghal akkor a második router fogja átvenni a szolgálatot.

### switch 1

Alapkonfiguráció
- megkapta az S1 nevet
- vlan 99ben megkapta a 192.168.99.3-as ip címet  

STP:
- azegyes számú és a kettes számú switchen van beállítva, hogy melyik switch melyik vlanokat kezelje ha mind kettő switch fut.

- Bpdu guard Port-fast rapid-pvst állítottunk még be a biztonság kedvéért

- ezen a routeren állítottung elsőbbséget az 1,9,28,29,10,20,40,50 számú vlanokon
- másodlagosba került a 30.31.32.42 számú vlanokon
- ha esetleg meghal ez a switch akkor átveszi a második switch az itt elsőbbséget élvező vlanokat.

Trönk:

- minden switch és router között

- Native vlan a vlan 100 

- statikus trönkölés van az gig0/1-16 amin enkedéjezve van a vlan 1,9,10,20,28,29,30,31,32,42,50,99,100

SSH:

- minden hálózati eszközön SSH használata

- második verziót állítottunk be az SSHnál

- domain névnek a trefort.hu

- felhasználónév amin el lehet érni: admin

- leszó hozzá: admin

- 2048 bites titkosított kulcsott generáltunk

- telnetett letiltottuk a nagyobb biztonság érdekébben

DAI:

- minden Switchen beállítva a src-mac, dst-mac, ip amik tovább növelik a biztonságot

### switch 2

Alapkonfiguráció
- megkapta az S1 nevet
- vlan 99ben megkapta a 192.168.99.3-as ip címet  


STP:
- azegyes számú és a kettes számú switchen van beállítva, hogy melyik switch melyik vlanokat kezelje ha mind kettő switch fut.

- Bpdu guard Port-fast rapid-pvst állítottunk még be a biztonság kedvéért

- ezen a routeren állítottung elsőbbséget az 30.31.32.42 számú vlanokon
- másodlagosba került a  1,9,28,29,10,20,40,50 számú vlanokon
- ha esetleg meghal ez a switch akkor átveszi a második switch az itt elsőbbséget élvező vlanokat.

Trönk:

- minden switch és router között

- Native vlan a vlan 100 

- statikus trönkölés van az gig0/1-16 amin enkedéjezve van a vlan 1,9,10,20,28,29,30,31,32,42,50,99,100

SSH:

- minden hálózati eszközön SSH használata

- második verziót állítottunk be az SSHnál

- domain névnek a trefort.hu

- felhasználónév amin el lehet érni: admin

- leszó hozzá: admin

- 2048 bites titkosított kulcsott generáltunk

- telnetett letiltottuk a nagyobb biztonság érdekébben

DAI:

- minden Switchen beállítva a src-mac, dst-mac, ip amik tovább növelik a biztonságot


### switch 3-12

Alapkonfiguráció
- nevük S és a számozása
- vlan 99 en a helyes ip cím

STP:

- A és B épület switchei között

- Bpdu guard

- Port-fast

- rapid-pvst

Trönk:

- minden switch és router között

- Native vlan 100

- Static trönkölés

SSH:

- minden hálózati eszközön SSH használata

- második verziót állítottunk be az SSHnál

- domain névnek a trefort.hu

- felhasználónév amin el lehet érni: admin

- leszó hozzá: admin

- 2048 bites titkosított kulcsott generáltunk

- telnetett letiltottuk a nagyobb biztonság érdekébben

DAI:

- minden Switchen

- src-mac, dst-mac, ip használata


### acces point
Vlan 40


### server 1
ip cím: 192.168.50.254
DNS 
- 192.168.50.254
- hozzá van adva a trefort.hu a 192.168.50.254-es ip címhez
Email
- felhazsnálónév admin jelszó admin
- domain cím : trefortszki.hu

### server 2
ip cím: 192.168.50.253
FTP
- admin fiók: felhasználónév admin jelszó: admin

WEB
- hozzá van adva a trefort2.hu a 192.168.50.254-es ip címhez