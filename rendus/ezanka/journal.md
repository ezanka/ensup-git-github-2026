# Carnet de bord
ezanka

## Mes preuves


#### index
L'index est la version actuel de chaque fichier pret a etre push, apres un add

### git diff
ethan@MacBook ensup-git-github-2026 % git log --oneline -- rendus/ezanka/acces.md 
53fe604 (HEAD -> main) docs: ajoute d'informations sur l'accès a l'école

la commande remonte le dernier commit du fichier

### id commit
4c3ad34 (HEAD -> main) docs: ajout de la date d'ouverture
fc62f68 (feature/accessibilite) docs: ajouter les indications d accessibilite

### pull request
https://github.com/AbidHamza/ensup-git-github-2026/pull/6

### fork
clone sur github

### clone
clone en local

### branch
créer un "environnement" distinct avec des fichiers et des modifications differente des autre branch

### PR collecte 
https://github.com/AbidHamza/ensup-git-github-2026/pull/6

### PR collecte 
https://github.com/ezanka/ensup-git-github-2026/pull/1

### Commentaire utile

### Commit 
745dbf9 (origin/feature/equipe, feature/equipe) docs:  information sur l'absense des coordination des salles


### Erreur de départ :
`git add` sur `brouillon.txt` trop tôt, corrigé avec `git restore --staged`.

### Deux propositions : 
`main` = 09h30, `feature/horaire` = 10h00 (même ligne de `horaire.txt`, donc conflit au merge).

### Décision retenue : 
le commanditaire valide 09h45, remplacé dans `horaire.txt`, marqueurs supprimés.

### Commandes de fin de fusion : 
`git add horaire.txt`, `git commit -m "fix: convenir de 09h45"`, `git status`.

### Parents du commit de fusion : 
10def57 (HEAD -> main) fix: convenir de 09h45
1718132 (feature/horaire) feat: proposer 10h00

## Fetch vs merge (push refusé)

### Pourquoi le push a été refusé : 
j'ai commité sur GitHub (`programme.md`) et en local (`README.md`) : les deux histoires ont avancé, `origin/main` contient un commit que je n'ai pas.

### Pourquoi `fetch` seul n'aurait pas ajouté la visite libre à mon fichier local : 
`git fetch origin` télécharge seulement les nouveaux commits dans `origin/main` (branche de suivi), sans toucher à ma branche `main` ni à mes fichiers. Il faut `git merge origin/main` (ou `git pull`) pour intégrer ces changements.

### Résultat : 
fusion sans conflit (fichiers différents : `programme.md` et `README.md`), commit de fusion "merge: recuperer le programme publie en ligne", puis push accepté sans `--force`.