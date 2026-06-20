Le portfolio est développé en HTML simple, avec un historique Git structuré : un commit initial sur main, puis une fonctionnalité (section Compétences) développée sur une branche isolée feature-competences et fusionnée via Pull Request en résolvant l'Issue associée. Une modification conflictuelle du titre a ensuite été simulée sur deux branches divergentes (main et conflict-test), démontrant la détection et la résolution manuelle d'un conflit Git. L'historique final, consultable via git log --oneline, retrace ainsi chaque étape du cycle collaboratif : création, branchement, fusion, conflit et stabilisation du code sur main.
## Commandes Git utilisées

# Initialisation
git init
git add index.html
git commit -m "Initialisation du portfolio"
git remote add origin https://github.com/ton-pseudo/bio-portfolio.git
git branch -M main
git push -u origin main

# Branche et fonctionnalité (Compétences)
git checkout -b feature-competences
git add index.html
git commit -m "Ajout de la section compétences"
git push -u origin feature-competences

# Pull Request et synchronisation
git checkout main
git pull origin main

# Simulation de conflit
git checkout -b conflict-test
git add index.html
git commit -m "Modification du titre sur conflict-test"
git push -u origin conflict-test

git checkout main
git add index.html
git commit -m "Modification directe du titre sur main"
git merge conflict-test

# Résolution du conflit
git add index.html
git commit -m "Résolution du conflit sur le titre"
git push origin main

# Vérification de l'état et de l'historique
git status
git branch
git log --oneline
