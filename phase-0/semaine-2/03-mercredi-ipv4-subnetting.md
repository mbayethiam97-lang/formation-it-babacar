# Mercredi Sem.2 — IPv4 + Subnetting CIDR

## Ce que j'ai fait aujourd'hui
- Compris les classes IPv4 et les plages privées
- Calculé des sous-réseaux /24 /26 /28 /30
- Atteint 80%+ sur SubnettingPractice.com

## Classes IPv4

Classe A : 1.0.0.0   – 126.0.0.0   → /8  → 16 millions hôtes
Classe B : 128.0.0.0 – 191.255.0.0 → /16 → 65 534 hôtes
Classe C : 192.0.0.0 – 223.255.255.0 → /24 → 254 hôtes

## Plages privées (RFC 1918) — à mémoriser !
10.0.0.0/8         → grandes entreprises
172.16.0.0/12      → entreprises moyennes
192.168.0.0/16     → réseaux domestiques

## Calcul sous-réseaux : formule 2^n - 2
/24 → 256 - 2 = 254 hôtes
/25 → 128 - 2 = 126 hôtes
/26 → 64  - 2 = 62  hôtes
/27 → 32  - 2 = 30  hôtes
/28 → 16  - 2 = 14  hôtes
/29 → 8   - 2 = 6   hôtes
/30 → 4   - 2 = 2   hôtes (liens point-à-point)

## Exemple : 192.168.1.0/26
Masque      : 255.255.255.192
Réseau      : 192.168.1.0
1er hôte    : 192.168.1.1
Dernier hôte: 192.168.1.62
Broadcast   : 192.168.1.63
Nb hôtes    : 62

## Source
- SubnettingPractice.com (20 exercices faits)
- Jeremy's IT Lab IPv4 Addressing

## Difficulté du jour
- []
- []
