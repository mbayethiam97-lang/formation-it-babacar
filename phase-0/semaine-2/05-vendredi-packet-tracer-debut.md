# Vendredi Sem.2 — Cisco Packet Tracer : 1er réseau

## Ce que j'ai fait aujourd'hui
- Installé Cisco Packet Tracer via NetAcad
- Créé mon premier réseau : 2 PCs + 1 switch
- Fait ping entre les machines
- Créé un 2e réseau avec un routeur

## Comment télécharger Packet Tracer
1. Aller sur netacad.com
2. Créer un compte gratuit
3. Chercher "Cisco Packet Tracer" dans les cours
4. Télécharger la version Linux ou Windows

## Lab 1 : 2 PCs + 1 Switch
Topologie :
  PC0 (192.168.1.1/24) ──┐
                          Switch0
  PC1 (192.168.1.2/24) ──┘

Câbles : câble droit (Copper Straight-Through)
Résultat : ping PC0 → PC1 = succès ✓

## Lab 2 : 2 PCs + 1 Routeur
Topologie :
  PC0 (192.168.1.1/24) ── G0/0 Routeur G0/1 ── PC1 (192.168.2.1/24)

Commandes routeur :
  enable
  configure terminal
  interface g0/0
  ip address 192.168.1.254 255.255.255.0
  no shutdown
  interface g0/1
  ip address 192.168.2.254 255.255.255.0
  no shutdown
  end
  show interfaces

## Câbles à retenir
Câble droit    → PC vers Switch, Switch vers Routeur
Câble croisé   → PC vers PC, Switch vers Switch (ancien)
Console        → PC vers Routeur pour configuration

## Source
- Cisco Packet Tracer via NetAcad (gratuit)
- Jeremy's IT Lab YT Introduction to Cisco Devices

## Difficulté du jour
- []
- []
