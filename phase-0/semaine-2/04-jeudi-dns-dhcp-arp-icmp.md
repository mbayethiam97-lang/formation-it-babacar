# Jeudi Sem.2 — DNS + DHCP + ARP + ICMP

## Ce que j'ai fait aujourd'hui
- Compris le rôle de chaque protocole de support
- Capturé DNS + ARP + ICMP dans Wireshark
- Annoté les couches OSI pour chaque protocole

## DNS — Domain Name System (port 53 UDP)
Rôle : traduit un nom de domaine en adresse IP
Exemple : google.com → 142.250.74.46
Commandes :
  nslookup google.com     → résolution DNS simple
  dig google.com          → résolution détaillée
Dans Wireshark : filtre "dns"
Couche OSI : Application (7)

## DHCP — Dynamic Host Configuration Protocol (ports 67/68 UDP)
Rôle : distribue automatiquement les IPs aux machines
Process DORA :
  D → Discover  (client cherche un serveur DHCP)
  O → Offer     (serveur propose une IP)
  R → Request   (client accepte l'IP proposée)
  A → Ack       (serveur confirme)
Dans Wireshark : filtre "bootp"
Couche OSI : Application (7)

## ARP — Address Resolution Protocol
Rôle : trouve l'adresse MAC à partir d'une IP
Exemple : "Qui a 192.168.1.1 ? Donne-moi ton MAC"
Commandes :
  arp -a                  → voir la table ARP locale
Dans Wireshark : filtre "arp"
Couche OSI : Data Link (2)

## ICMP — Internet Control Message Protocol
Rôle : tester la connectivité réseau (ping)
Commandes :
  ping 8.8.8.8            → tester connexion Internet
  ping -c 4 192.168.1.1   → 4 paquets seulement
  traceroute google.com   → tracer le chemin réseau
Dans Wireshark : filtre "icmp"
Couche OSI : Network (3)

## Source
- Jeremy's IT Lab YT DNS+DHCP+ARP
- Wireshark + captures personnelles

## Difficulté du jour
- []
- []
