# Mardi Sem.1 — Gestion de fichiers Linux

## Ce que j'ai fait
- Créé /projets/reseau/semaine1 avec sous-dossiers
- Copié, renommé, supprimé des fichiers en CLI pur
- Exploré /etc et /var/log

## Commandes apprises

cp fichier destination      → copier un fichier
mv fichier destination      → déplacer OU renommer un fichier
rm fichier                  → supprimer un fichier
rm -rf dossier              → supprimer un dossier entier (DANGER)
cat fichier                 → afficher tout le contenu d'un fichier
less fichier                → afficher page par page (q pour quitter)
head -n 5 fichier           → voir les 5 premières lignes
tail -n 5 fichier           → voir les 5 dernières lignes
find / -name "*.txt"        → chercher des fichiers par nom

## Lab réalisé
- Créé 5 fichiers : config1.txt à config5.txt
- Copié tous les fichiers vers un dossier backup/
- Renommé config1.txt en routeur-principal.txt
- Supprimé config5.txt

## Ce que j'ai retenu
- mv sert aussi à renommer, pas besoin de copier puis supprimer
- rm -rf est irréversible, il n'y a pas de corbeille en CLI
- tail -f permet de suivre les logs en temps réel

## Difficulté du jour
- []
- []

## Sources
- NetAcad NDG Linux Module 3
- LinuxJourney.com Files
