# Configuration de Base d'un Routeur Cisco IOS

## Commandes appliquées dans le lab Packet Tracer

````ios
Router> enable
Router# configure terminal

! Nom du routeur
Router(config)# hostname R1

! Désactiver la résolution DNS (évite les délais sur fautes de frappe)
R1(config)# no ip domain-lookup

! Message de bannière (avertissement légal)
R1(config)# banner motd #
===========================================
ACCES AUTORISE UNIQUEMENT — LAB BABACAR
===========================================
#

! Chiffrer TOUS les mots de passe en clair dans running-config
R1(config)# service password-encryption

! Mot de passe mode privileged
R1(config)# enable secret MonMotDePasse123

! Sauvegarder la configuration
R1# copy running-config startup-config
````

## Vérifications importantes
````ios
R1# show running-config       ! Voir config active
R1# show version              ! Version IOS, uptime, RAM
R1# show startup-config       ! Config sauvegardée en NVRAM
````

## Résultat observé dans Packet Tracer
- Invite passe de Router> à R1>  ✅
- Banner s'affiche à la connexion ✅
- Mots de passe chiffrés dans show running-config ✅
- no ip domain-lookup : plus de délai sur erreur de frappe ✅
