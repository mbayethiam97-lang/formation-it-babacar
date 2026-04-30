# Lab Packet Tracer — Configuration SSH Complète

## Topologie
````
PC0 (192.168.1.10) ──── Switch ──── R1 (G0/0: 192.168.1.1)
````

## Étapes de configuration SSH sur R1

### Étape 1 — Prérequis : hostname + domaine (obligatoires pour générer les clés)
````ios
R1(config)# hostname R1
R1(config)# ip domain-name lab.local
````

### Étape 2 — Générer la paire de clés RSA 2048 bits
````ios
R1(config)# crypto key generate rsa modulus 2048
! Output attendu :
! The name for the keys will be: R1.lab.local
! % Generating 2048 bit RSA keys, keys will be non-exportable...
! [OK] (elapsed time was 3 seconds)
````

### Étape 3 — Créer un utilisateur local avec mot de passe chiffré
````ios
R1(config)# username admin privilege 15 secret AdminSecure2024
````

### Étape 4 — Forcer SSH v2 uniquement
````ios
R1(config)# ip ssh version 2
````

### Étape 5 — Configurer les lignes VTY pour SSH uniquement
````ios
R1(config)# line vty 0 4
R1(config-line)# transport input ssh
R1(config-line)# login local
R1(config-line)# exec-timeout 5 0
R1(config-line)# exit
````

### Étape 6 — Désactiver Telnet sur la console aussi
````ios
R1(config)# line console 0
R1(config-line)# login local
R1(config-line)# exec-timeout 10 0
R1(config-line)# exit
````

### Étape 7 — Sauvegarder
````ios
R1# copy running-config startup-config
````

## Vérifications
````ios
R1# show ip ssh
! SSH Enabled - version 2.0
! Authentication timeout: 120 secs; Authentication retries: 3

R1# show users
! Voir les sessions actives

R1# show running-config | section line vty
! Vérifier transport input ssh
````

## Test depuis PC0 (Packet Tracer → Desktop → Terminal)
````
SSH -l admin 192.168.1.1
Password: AdminSecure2024
R1#
````

## Résultat obtenu
- Connexion SSH réussie ✅
- Telnet refusé sur port 23 ✅
- Clés RSA 2048 bits générées ✅
- Mot de passe chiffré (secret) dans running-config ✅

## Ce que j'ai appris
- Sans ip domain-name → impossible de générer les clés RSA
- `secret` = chiffrement MD5/Scrypt → TOUJOURS utiliser secret et jamais password
- `privilege 15` = accès direct au mode Privileged EXEC après login
- `exec-timeout 5 0` = déconnexion auto après 5 minutes d'inactivité (sécurité)
