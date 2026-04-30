# Cisco IOS — Les 3 Modes Principaux

## Mode 1 : User EXEC
- Invite : Router>
- Accès : connexion initiale
- Limité : show limité, pas de config
- Commande pour monter : enable

## Mode 2 : Privileged EXEC
- Invite : Router#
- Accès : après enable (+ mot de passe si configuré)
- Permet : show complet, debug, copy, reload
- Commande pour monter : configure terminal

## Mode 3 : Global Configuration
- Invite : Router(config)#
- Accès : après configure terminal
- Permet : TOUT configurer
- Sous-modes : interface / line / router

## Sous-modes importants
| Sous-mode         | Invite                    | Accès                        |
|-------------------|---------------------------|------------------------------|
| Interface         | Router(config-if)#        | interface GigabitEthernet0/0 |
| Line VTY          | Router(config-line)#      | line vty 0 4                 |
| Line Console      | Router(config-line)#      | line console 0               |
| Routing Protocol  | Router(config-router)#    | router ospf 1                |

## Navigation entre les modes
| Commande        | Action                                      |
|-----------------|---------------------------------------------|
| enable          | User EXEC → Privileged EXEC                 |
| configure terminal | Privileged EXEC → Global Config          |
| exit            | Retour au mode précédent                    |
| end / Ctrl+Z    | Retour direct au Privileged EXEC            |
| disable         | Privileged EXEC → User EXEC                |
