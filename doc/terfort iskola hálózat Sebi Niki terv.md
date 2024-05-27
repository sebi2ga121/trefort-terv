-B épület
szerverteremben helyezkedig el a 1. 2. switch amik között stp protokol és még van 2 router és két szerver

a két router rá van kötve az ISPre külön külön

mind két router össze van kötve mind a három switchel, mivel a routereken HSRP protokolt fogunk használni így elérjük a redundanciát a hálózatban

az 1. switch kiszolgál még másik 12 switchet ami négy gépterembe vezet
ezek a géptermek külön Vlanokban lenne Vlan(1,9,28,29) (egy gépteremben átlagosan 20 géppel számolva)

a 2. switch is hozzá van kötve a 12 switchhez ami a maradég gépterembe vezet
ezek a géptermek külön Vlanokban lenne Vlan(30,31,32,42) (egy gépteremben átlagosan 20 géppel számolva)

2 switch a maradék gépeket szolgálja ki amik a B épület sima termeiben vannak (külön Vlan a szerverszobának, tanárinak, igazgató helyettes szobákba, tanári gépeknek a termekben és a karbantartóknak), 2 pedig az A épületben lesz



stp protokol lesz a switcheken
ssh védelem lesz minden hálózati eszközön
dhcp protokol fog kerülni a routerekre a wifihez. A számítógpeknek manuálisan adunk ip címet hogy tudjuk melyik gép hova tartozik
teljeskörű védelem minden hálózati eszközön

a kétt szerver közül az egyiken DNS, Email a másikon weblap és Ftp protokoll lesz



-A épület
Az A épületben el van helyezve a két switch a tanáriban. Az 1. és 2. emeleten a tanári az igazgatói és igazgatói helyettes gépek külön Vlant kapnak és a termekbe pedig kihuzunk kábeleket az ott lévő tanári gépekhez.



Az access point-okat is rákötnénk a hálózatra. Külön lenne választva a tanári és a quest wifi és a prioritás a tanárok wifijén lesz. Az A épületben a tanáriba kerülne egy access point és az első emelet túl oldalára kerülne egy másik (természetesen egy komolyabb access point ami kielégíti az igényeket)

A B épületben 4 darab access pontot tervezek. 1. emeleten az ebédlőben a másik az orvosiban. A másik kettő a 3. emeleten az igazgató helyettes teremben és a b31-es teremben.



A kábelvezetés a szerverszobából indulna minden felé és lyuk furrással és kábelvezetővel oldanánk meg a kábelek elvezetését

A két épület között maradna az a megoldás, hogy egy kifeszített sodrott drótra rátekernénk azt a 6 vagy 8 ethernet kábelt ami átmegy a szerveszobától az A épület általános tanáriba és ott lenne elhelyezve a másik kettő switch amiből elvezetnénk a kábeleket a termekbe.

Természetesen mindenhol gigabites kábelt használunk és minden eszköz képes lesz használni a gigabites sebességet



-Eszközök:

router: cisco isr 4451
switch: Cisco CBS350-24T-4G-EU Managed 24-port GE, 4x1G SFP
access point: cisco business 150 ax