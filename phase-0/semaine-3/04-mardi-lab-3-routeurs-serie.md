# Lab Packet Tracer — 3 Routeurs en Série

## Topologie
````
PC0 ──── R1 ──── R2 ──── R3 ──── PC1
192.168.1.0/24  10.0.12.0/30  10.0.23.0/30  192.168.3.0/24
````

## Plan d'adressage

| Équipement | Interface | Adresse IP       | Masque            |
|------------|-----------|------------------|-------------------|
| PC0        | NIC       | 192.168.1.10     | 255.255.255.0     |
| R1         | G0/0      | 192.168.1.1      | 255.255.255.0     |
| R1         | G0/1      | 10.0.12.1        | 255.255.255.252   |
| R2         | G0/0      | 10.0.12.2        | 255.255.255.252   |
| R2         | G0/1      | 10.0.23.1        | 255.255.255.252   |
| R3         | G0/0      | 10.0.23.2        | 255.255.255.252   |
| R3         | G0/1      | 192.168.3.1      | 255.255.255.0     |
| PC1        | NIC       | 192.168.3.10     | 255.255.255.0     |

## Configuration R1
````ios
R1(config)# interface GigabitEthernet0/0
R1(config-if)# ip address 192.168.1.1 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)# interface GigabitEthernet0/1
R1(config-if)# ip address 10.0.12.1 255.255.255.252
R1(config-if)# no shutdown
R1(config-if)# end
R1# show ip interface brief
````

## Configuration R2
````ios
R2(config)# interface GigabitEthernet0/0
R2(config-if)# ip address 10.0.12.2 255.255.255.252
R2(config-if)# no shutdown
R2(config-if)# exit
R2(config)# interface GigabitEthernet0/1
R2(config-if)# ip address 10.0.23.1 255.255.255.252
R2(config-if)# no shutdown
R2(config-if)# end
````

## Configuration R3
````ios
R3(config)# interface GigabitEthernet0/0
R3(config-if)# ip address 10.0.23.2 255.255.255.252
R3(config-if)# no shutdown
R3(config-if)# exit
R3(config)# interface GigabitEthernet0/1
R3(config-if)# ip address 192.168.3.1 255.255.255.0
R3(config-if)# no shutdown
R3(config-if)# end
````

## Vérification
````ios
R1# show ip interface brief
R1# ping 10.0.12.2        ! ping vers R2 ✅
R1# ping 10.0.23.2        ! échoue sans routes statiques ❌ (normal)
````

## Ce que j'ai appris
- /30 = exactement 2 hôtes utiles → parfait pour liens point-à-point entre routeurs
- Sans routes statiques ou protocole de routage, les routeurs ne connaissent que leurs réseaux directement connectés
- no shutdown est INDISPENSABLE, toutes les interfaces Cisco sont shutdown par défaut
