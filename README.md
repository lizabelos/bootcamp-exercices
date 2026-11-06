# Partie 1 - Git

Bonjour
Test

## Étape 1 - manipulations de base

Utiliser le *shell* pour exécuter diverses sous-commandes de Git (lorsque l'on
exécute `git something ...`, `git` est la commande et `something` est la
sous-commande) :

- `git status` permet de consulter la liste des fichiers modifiés, et `git diff`
  d'afficher fichier par fichier les différences ;
- utiliser `git add files` et `git commit -m '...'` pour enregistrer les
  modifications dans différents commits ;
- utiliser `git status` pour s'assurer que toutes les modifications ont bien été
  enregistrées, et `git log` pour consulter l'historique ;

Après avoir modifié plusieurs fichiers (*p. ex.* fichiers Wikipedia ou script
Python), utiliser des variantes :

- exécuter `git status` depuis différents répertoires pour constater que la
  liste des fichiers modifiés est donnée relativement au répertoire courant ;
- enregistrer un ou plusieurs commits, en utilisant `git diff` immédiatement
  avant et `git diff --staged` immédiatement après `git add` pour constater
  comment les différences passent de la copie de travail à l'index ;
- utiliser `git restore --staged` pour enlever des différences de l'index ;
- après avoir enregistré toutes les modifications (et vérifié que c'est bien le
  cas via `git status`), utiliser `git log` pour lister les commits avec leurs
  identifiants et utiliser `git show commit-identifier` pour afficher le
  *diff* relatif à un commit.


## Étape 2 - manipulations avancées

Utiliser le *shell* pour exécuter des sous-commandes de Git permettant de
naviguer dans l'historique :

- utiliser `git checkout commit-identifier` pour mettre la copie de travail
  dans l'état correspondant au commit passé ;
- constater que le contenu des fichiers a bien été modifié ;
- retourner au point le plus avancé de l'historique en exécutant `git checkout main`,
  et constater que la copie de travail a de nouveau été modifiée ;
- utiliser `git rm files` pour supprimer un ou plusieurs fichiers ;
- constater la disparition du fichier de la copie de travail, et utiliser
  `git status` pour constater que la délétion fera partie du prochain commit ;
- enregistrer avec `git commit` la ou les délétions ;
- utiliser `git checkout` pour revenir à un point antérieur aux délétions et
  constater à nouveau que la copie de travail a été modifiée (en particulier,
  les fichiers supprimés sont de nouveau présents) ;
- revenir au point le plus avancé de l'historique en exécutant `git checkout main`.


# Partie 2 - GitHub

## Étape 1 - utilisation de branches

Utiliser le *shell* pour exécuter des sous-commandes de Git permettant de créer
une seconde branche et de passer d'une branche à l'autre :

- créer une seconde branche en exécutant `git branch name` ;
- utiliser `git branch` pour lister les branches (l'étoile indique la branche
  courante) ;
- utiliser `git switch name` pour passer sur la seconde branche, et vérifier
  avec `git branch` que le changement est effectif ;
- modifier un ou plusieurs fichiers et enregistrer un commit avec ces
  changements ;
- utiliser `git log` pour consulter l'historique de la branche ;
- utiliser `git switch main` pour revenir sur la branche principale puis
  `git log` pour voir que le commit additionnel n'est pas présent ;
- modifier un ou plusieurs *autres* fichiers et enregistrer un commit avec ces
  changements ;
- repasser sur la seconde branche avec `git switch name` et consulter
  l'historique ;
- utiliser `git rebase main` pour intégrer les modifications ajoutées à la
  branche principale ;
- utiliser `git log` pour vérifier que ces modifications ont bien été ajoutées.

Pour finir, répéter les étapes que ci-dessus, mais en modifiant les *mêmes lignes
des mêmes fichiers, avec des contenus différents, dans les deux branches*.
L'étape de `rebase` va échouer du fait de conflits :

- utiliser `git status` pour déterminer les fichiers contenant des conflits ;
- éditer ces fichiers pour résoudre les conflits (marqueurs `<<<<<<<` et `>>>>>>>`) ;
- utiliser `git add files` pour indiquer à Git que les conflits ont été
  résolus ;
- utiliser `git rebase --continue` pour poursuivre le rebase, qui doit cette
  fois être un succès ;
- utiliser `git log` pour constater que les modifications qui n'étaient
  originellement que sur la branche principale sont maintenant également sur la
  seconde branche.


## Étape 2 - ouverture d'une pull request

- utiliser `git add` et `git commit` pour sauvegarder d'éventuelles modifications
  pendantes ;
- utiliser `git push` pour pousser les changements vers le fork créé ;
- aller sur la page GitHub du *fork* (donc hors l'interface de VS Code) ;
- cliquer sur le bouton "Contribute" puis le bouton "Open pull request" dans la
  fenêtre alors ouverte ;
- la page GitHub affichée est alors celle qui permet l'ouverture d'une *pull request*
  sur le dépôt de départ (*i. e.* celui depuis lequel le *fork* été créé) ;
- entrer un titre et un descriptif, puis cliquer sur "Create pull request" ;
- la page GitHub affichée montre alors la *pull request* créée ;
- utiliser les onglets "Commits" et "Files changed" pour consulter respectivement
  la liste de commits poussés plut tôt et afficher le *diff* correspondant à ces
  commits.

Liza