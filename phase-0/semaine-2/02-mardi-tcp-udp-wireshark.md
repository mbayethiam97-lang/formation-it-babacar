# Mardi Sem.2 — TCP 3-way handshake + Wireshark

## Ce que j'ai fait aujourd'hui
- Compris la différence TCP vs UDP
- Capturé mon premier trafic réseau avec Wireshark
- Identifié les couches OSI dans une capture

## TCP vs UDP

TCP (Transmission Control Protocol)
- Connexion obligatoire avant envoi (3-way handshake)
- SYN → SYN-ACK → ACK
- Fiable, ordonné, accusé de réception
- Utilisé par : HTTP, HTTPS, SSH, FTP

UDP (User Datagram Protocol)
- Pas de connexion, envoi direct
- Pas d'accusé de réception
- Rapide mais non fiable
- Utilisé par : DNS, DHCP, streaming, jeux

## Ports importants à mémoriser
22   → SSH
53   → DNS
80   → HTTP
443  → HTTPS
21   → FTP
25   → SMTP
67/68 → DHCP

## Ce que j'ai vu dans Wireshark
- Frame (couche 2) → Ethernet
- Internet Protocol (couche 3) → IP src/dst
- TCP (couche 4) → ports + flags SYN/ACK
- HTTP (couche 7) → GET / HTTP/1.1

## Commandes pratiques
wireshark                    → ouvrir l'interface graphique
ping google.com              → générer du trafic ICMP à capturer
filter Wireshark : tcp       → voir seulement TCP
filter Wireshark : icmp      → voir seulement ping

## Source
- Wireshark wireshark.org
- Jeremy's IT Lab YT OSI and TCP/IP Model

## Difficulté du jour
- []
- []
