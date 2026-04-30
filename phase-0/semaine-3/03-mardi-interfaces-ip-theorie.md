# Adressage IP sur Interfaces Cisco IOS

## Commandes essentielles

| Commande                              | Description                        |
|---------------------------------------|------------------------------------|
| interface GigabitEthernet0/0          | Entrer dans l'interface G0/0       |
| ip address 192.168.1.1 255.255.255.0  | Assigner une IP + masque           |
| no shutdown                           | Activer l'interface (UP)           |
| shutdown                              | Désactiver l'interface (DOWN)      |
| show interfaces                       | Voir état détaillé de toutes les if|
| show ip interface brief               | Résumé rapide : IP + statut        |

## Lire la sortie de "show ip interface brief"

| Interface   | IP-Address    | OK? | Method | Status | Protocol |
|-------------|---------------|-----|--------|--------|----------|
| Gi0/0       | 192.168.1.1   | YES | manual | up     | up       |
| Gi0/1       | 10.0.0.1      | YES | manual | up     | up       |
| Gi0/2       | unassigned    | YES | unset  | admin  | down     |

- Status "up" + Protocol "up" = interface fonctionnelle ✅
- Status "admin down" = shutdown appliqué manuellement ❌
- Status "up" + Protocol "down" = problème câble/couche 2 ⚠️
