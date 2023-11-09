# Exemple pour le cours versioning de code - l'outil Git

## EFREI 03/10/2022

# Titre H1

## Titre H2

### Titre H3

#### Titre H4

##### Titre H5

###### Titre H6

_Je suis un super paragraphe en italique_\
_avec retour à la ligne_\
**Je suis un paragraphe en gras.**

| Syntax    | Description | Test  |
| :-------- | :---------: | ----: |
| Header    | Title       | Texte |
| Texte exemple aligné à gauche | Texte exemple centré | Texte exemple aligné à droite |

## Points vus le 05/10/2023

Nous avons vu les commandes terminal suivantes :

1. pwd : permet de savoir où l'on se trouve au sein de l'arborescence du système de fichiers
2. ls : (options -a, -l, -A) permet d'afficher la liste des dossiers et fichiers ainsi que les droits qui leurs sont liés
3. cd : permet de se déplacer dans l'arborescence du système de fichiers (. = dossier courant, .. = dossier parent)
4. mkdir : permet de créer un dossier
5. touch : permet de créer un fichier
6. rmdir : permet de supprimer un dossier
7. rm : permet de supprimer un fichier / dossier (avec l'option de récursivité -r)
8. cat / less / more <file_name> : afficher le contenu d'un fichier
9. clear : nettoyer le terminal

## Fonctionnement

Afin de pouvoir faire fonctionner ce projet, vous devrez créer, à la racine du dossier parent, un fichier secret.txt contenant les client_secret et client_key.

## Résumé matinée

| Commande | Options | Fonction |
| :------ | :-----: | :------: |
| `git init` | | Initialiser un projet Git |
| `git config user.email` | | Définir l'e-mail de l'utilisateur courant pour Git |
| `git config user.name` | | Définir le nom de l'utilisateur courant pour Git |
| `git status` | | Afficher le statut actuel de la branche courante |
| `git add` | | "Stage" un ou plusieurs fichiers |
| `git commit` | --amend | Modifier le message du dernier commit |
| `git commit` | -m | Ajouter un message au commit en ligne de commande |
| `git tag` | [-a, -m, -d, -f] [commit or tag number] | Ajouter, supprimer ou déplacer un tag sur un commit donné |
| `git show` | [commit number] | Afficher les informations relatives à un commit donné |
| `git diff` | [file] | Afficher les changements entre maintenant et le dernier commit sur un ou tous les fichiers |
| `git log` | | Afficher la liste des commits sur la branche actuelle |
| `git reset` | --soft, --hard | Revenir à un état précédent de notre code projet |
| `git ls-files` | | Liste les fichiers suivis par Git |
| `git rm` | --cached | | Retirer un ou plusieurs fichiers de l'historique de suivi de Git |
| `git restore` | --staged | | Unstage un ou plusieurs fichiers |
| `git branch` | -M, -d, -a (--all) | Créer ou renommer une branche de travail |
| `git checkout` | -b | (Créer si l'option -b a été donnée et) Se positionner sur une branche de travail |
| `git merge` | | Permet de fusionner l'historique Git de deux branches |
| `git remote add <alias> <url dépôt distant>` | | Ajoute un alias lié à une URL de dépôt distant |
| `git remote` | -v | Lister les différentes origines distantes |
| `git pull [<alias> <branche>]` | -u (--set-upstream) | Récupérer les infos d'une branche distante et les fusionner avec la branche courante (équivalent git fetch + git merge) |
| `git push [<alias> <branche>]` | -u (--set-upstream) | Envoi le code source et l'historique des versions sur le dépôt distant mentionné
| `git stash` | | Retire et stocke en mémoire les changements non commités de la branche actuelle |
| `git stash apply` | | Applique les changements du dernier patch sur la branche courante |
| `git cherry-pick`  | | Applique un commit donné dans la branche de travail |

## Création d'un compte GitHub

Aller sur [github](https://github.com/) et cliquer sur "Sign up" pour lancer le processus de création de compte.

## Génération d'une clé SSH

```bash
ssh-keygen
```

Laisser les valeurs par défaut (appuyer plusieurs fois sur la touche Entrée).

Localiser la clé publique (par défaut : C:\Users\<username>\.ssh\) et copier le contenu du fichier id_rsa.pub.

Aller sur github dans les paramètres du compte (icône du compte en haut à droite de l'écran d'accueil >> settings >> SSH and GPG keys >> New SSH Key) et ajouter la clé nouvellement créée et copiée.

## Exercice 1

Dans votre branche main :

1. Créer une nouvelle branche avec la commande `git branch <branche>`
2. Appliquer des modifications sur un ou plusieurs fichiers.
3. Sauvegarder vos changements et les envoyer dans le dépôt distant.

Dans la branche que vous venez de créer à l'étape précédente :

1. Récupérer les informations de la branche main depuis le dépôt distant.
2. Fusionner ces changements dans cette nouvelle branche.
3. Appliquer des modifications dans un ou plusieurs fichiers dans cette nouvelle branche.
4. Sauvegarder les modifications et les envoyer dans le dépôt distant (sur la bonne branche, pas sur main !).

Dans la branche main :

1. Vous allez récupérer et fusionner les informations depuis l'autre branche sur le dépôt distant (une seule commande cette fois-ci).
2. Vous allez apporter des modifications sur le fichier README.md (ce que vous voulez).
3. Vous allez stocker ces changements via la commande `git stash`.

Dans l'autre branche :

1. Vous appliquerez les changements contenus dans le stash via la commande `git stash apply`.

## Exercice 2

(travail en binôme)

1. L'un des deux membres du binôme (OWNER) donne accès à l'autre à son dépôt distant (Settings > Collaborators > Add new collaborator).

2. L'autre (COLLABORATOR) va cloner le projet du premier sur son Bureau (NE PAS créer un dossier manuellement, l'opération est automatique !) avec la commande `git clone <url> [<nom dossier>]`

3. Maintenant, COLLABORATOR et OWNER vont tous deux travailler sur le même dépôt, envoyer leurs modifications dans le dépôt distant, sur la même branche ou sur des branches séparées, et récupérer à intervalle régulier les changements effectués existants dans le dépôt distant.

Le but de cet exercice est de simuler un travail en groupe. Evitez donc, si vous souhaitez ajouter un peu de réalisme, de communiquer quant à vos push et pull respectifs.

## Exercice 3 : création d'un projet git de toutes pièces

(travail seul)

1. Créez un nouveau dossier sur votre Bureau à l'aide de la commande `mkdir`
2. Positionnez-vous dans le dossier nouvellement créé à l'aide de la commande `cd`
3. A l'aide de la commande `touch`, créez deux fichiers nommés "README.md" et ".gitignore" (sans les guillemets, bien évidemment...)
4. Initialisez un nouveau dépôt pour votre projet
5. Insérez le contenu suivant dans votre fichier README.md :

    ## Projet d'exercice Git

    ### Démarrage du projet

    Le projet a été démarré le 26/10/2023 et a pour objectif d'apprendre à utiliser l'outil Git Client.

6. Créez un commit afin de sauvegarder les changements apportés au fichier `README.md`.
7. Créez une nouvelle branche de travail que vous appelerez `development` à partir de la branche `main`
8. A partir de la branche `development`, créez une nouvelle branche appelée `feat/gitignore`, puis positionnez-vous sur cette nouvelle branche
9. Ajoutez le contenu suivant dans le fichier `.gitignore` :
    node_modules
    src
    .env
    .env.development.local
    .env.test.local
    .env.production.local
    .env.local
    logs
10. Créez un commit afin de sauvegarder les changements apportés au fichier `.gitignore`
11. **Après vous être repositionné dans la branche** `development`, créez une nouvelle branche appelée `feat/hello-world`
12. Dans cette nouvelle branche, à l'aide de la commande `touch`, créez un nouveau fichier appelé `index.js`
13. Dans ce fichier `index.js`, ajoutez le contenu suivant :

    (function sayHello() {
      return `Hello world!`;
    })();

14. Créez un commit afin de sauvegarder les changements apportés au projet
15. Maintenant, allez sur le site github.com et créez un nouveau dépôt (repository)
16. Dans votre projet local, ajoutez l'url distante de votre dépôt Github en lui donnant pour alias `origin`
17. Positionnez-vous sur votre branche `main` et sauvegardez-là sur votre dépôt distant
18. Placez-vous dans vos autres branches et effectuez la même opération que pour l'étape 17
19. Récupérez le numéro de commit de la branche `feat/gitignore` qui ajoute des infos dans le fichier `.gitignore` puis positionnez-vous dans la branche `feat/hello-world`
20. A l'aide de la commande `git cherry-pick`, appliquez les changements du commit récupéré sur la branche `feat/gitignore` sur votre branche de travail courante
21. Envoyez ces changements sur le dépôt distant dans la branche distante `feat/hello-world`
22. **Après vous être repositionné dans la branche** `development`, créez une nouvelle branche appelée `feat/update-readme` puis positionnez-vous dessus
23. Ajoutez le contenu suivant dans le fichier `README.md` :

    ## Nouveauté

    Un fichier index.js a été créé et contient notre première fonction !

24. Sauvegardez ces modifications à l'aide d'un commit et envoyez les changements dans votre dépôt distant
25. Depuis l'interface de Github, créez une pull request afin de fusionner les commits présents dans la branche `feat/update-readme` dans la branche `development`
26. Validez la pull request
27. Dans votre dépôt local, récupérez les changements de la branche distante `development` dans votre branche locale `development`
28. Positionnez-vous à présent dans votre branche `feat/hello-world` et procéder à un `git rebase` de la branche development
29. Ajoutez un changement de votre choix dans la branche `feat/hello-world` puis sauvegardez-le au moyen d'un commit que vous enverrez dans le dépot distant
30. Au moyen d'une pull request, fusionnez les commits de la branche `feat/hello-world` dans la branche `development`
31. Dans votre dépôt local, positionnez-vous sur la branche `development` et récupérez les changements pour cette branche présents dans le dépôt distant
32. Enfin, fusionnez la branche `development` dans la branche `main` au moyen de la commande `git merge`
