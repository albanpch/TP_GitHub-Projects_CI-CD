### Reponse aux questions TP — l’intégration continue avec GitHub Actions

## 1. Créer le projet en local

**Question 1.** Quelle est la différence entre `git init`, `git add` et `git commit` ?

`git init:` Initialise le dépôt github.
`git add:` Ajoute des modifications en liste d'attente `Staging Area`.
`git commit` Enregistre le fichier sous forme de `Snapshot`.

**Question 2.**

1. Quelle est la différence entre un dépôt local et un dépôt distant ?
Le dépôt local est stocké sur notre machine tandis que le dépot distant est stocké par github.
2. À quoi correspond le nom `origin` ?
`origin` est le nom qui lie le Git a l'URL du dépôt.
3. Quel est le rôle de la commande `git push` ?
`git push` envoie les commit vers le dépôt Github.
4. À quoi sert l'option `-u` dans `git push -u origin main` ?
`-u` Etablit une liaison de suivi (tracking) entre votre branche locale main et la branche distante main sur origin.

**Questions 3.** Quel est l’intérêt d’un environnement virtuel ? Pourquoi le test de division par zéro peut-il réussir alors que le programme lève une exception ?
L'intéret d'avoir un environnement virtuel est  d'éviter les conflits de versions entre différents projets.Il permet d'exporter facilement des dossiers
Le test de la divison par 0 permet de vérifier qu'une fonction réagit correctement en cas d'erreur.

**Question 4.** Pourquoi le premier push sur `main` déclenche-t-il automatiquement la CI alors qu'aucune pull request n'a encore été créée ?
La CI python est configurée pour qu'il se déclenche dès le premier `git push`.

**Question 5.** Pourquoi le test détecte-t-il la régression ? Que vous apprend le journal que l’icône rouge ne montre pas ?
Lorsqu'une modification du code altère involontairement un comportement qui fonctionnait auparavant (une régression), la sortie réelle ne correspond plus à la valeur attendue par le test. Le test échoue alors automatiquement lors de l'exécution de la CI, bloquant l'intégration du code défectueux avant qu'il n'atteigne la branche principale ou la production.