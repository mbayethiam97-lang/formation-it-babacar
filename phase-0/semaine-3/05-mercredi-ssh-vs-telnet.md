# SSH vs Telnet — Pourquoi SSH est Obligatoire

## Comparaison

| Critère          | Telnet              | SSH                        |
|------------------|---------------------|----------------------------|
| Port             | TCP 23              | TCP 22                     |
| Chiffrement      | ❌ Aucun            | ✅ AES, ChaCha20           |
| Mot de passe     | En clair sur réseau | Chiffré                    |
| Intégrité données| ❌ Non              | ✅ HMAC                    |
| Auth par clé     | ❌ Non              | ✅ RSA/ECDSA               |
| Utilisation 2024 | ❌ Interdit en prod | ✅ Standard industrie      |

## Pourquoi Telnet est dangereux
- Wireshark peut capturer le mot de passe en clair en temps réel
- N'importe qui sur le même réseau voit tout ce que tu tapes
- Interdit dans tous les environnements professionnels

## SSH version 2 — À toujours forcer
````ios
ip ssh version 2
````
