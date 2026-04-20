# Vendredi Sem.1 — chmod + clé SSH GitHub

## Ce que j'ai fait
- Compris le système de permissions Linux
- Généré une paire de clés SSH
- Connecté GitHub sans mot de passe

## Permissions Linux

chmod 755 fichier  → propriétaire tout | groupe lire+exécuter
chmod 644 fichier  → propriétaire lire+écrire | autres lire
chmod 600 fichier  → propriétaire seulement (pour clés privées SSH)
chown user fichier → changer le propriétaire d'un fichier

## Calcul des chiffres chmod

4 = lecture (r)
2 = écriture (w)
1 = exécution (x)

7 = 4+2+1 = rwx → tous les droits
6 = 4+2   = rw- → lire et écrire
5 = 4+1   = r-x → lire et exécuter
4 = 4     = r-- → lire seulement

Exemple : chmod 755
→ propriétaire : 7 = rwx (tout)
→ groupe       : 5 = r-x (lire + exécuter)
→ autres       : 5 = r-x (lire + exécuter)

## Configuration clé SSH GitHub

# Générer la paire de clés
ssh-keygen -t ed25519 -C "mbayethiam97@gmail.com"
→ Appuyer Entrée à chaque question (valeurs par défaut)

# Deux fichiers sont créés
~/.ssh/id_ed25519      → clé PRIVÉE (ne jamais partager)
~/.ssh/id_ed25519.pub  → clé PUBLIQUE (à donner à GitHub)

# Afficher la clé publique pour la copier
cat ~/.ssh/id_ed25519.pub

# Tester la connexion SSH avec GitHub
ssh -T git@github.com
→ Résultat attendu : "Hi babacar! You've successfully authenticated"

# Changer l'URL du repo en SSH
git remote set-url origin git@github.com:TON-USERNAME/formation-it-babacar.git

## Pourquoi SSH plutôt que mot de passe
- Plus sécurisé (clé cryptographique)
- Connexion automatique sans saisir de mot de passe
- Standard dans toutes les entreprises

## Difficulté du jour
- []
- []

## Sources
- GitHub Docs SSH Keys
- GitHub Skills
