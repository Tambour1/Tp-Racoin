## Première étape - L'analyse
- [x] Trouver le ou les langages utilisé
- [x] Trouver le ou les framework principaux utilisé
- [x] Trouvez le but général de l'application
- [x] Faire une première estimation de ce qu'il faut pour faire marcher l'application

### L'analyse
- Comme langages utilisés on retrouve du PHP, du SQL avec une base de données MySQL, du JavaScript et du SCSS/CSS.
- Comme framework on retrouve Twig et SLIM.
- Cette application est une application de petites d'annonces comme Leboncoin (Structure de la bdd nous donne des indices)
- Pour faire fonctionner l'application, je pense qu'il faut d'abord lancer le docker compose et ensuite accéder à "index.php" dans le navigateur.

## Deuxième étape - La prise en main
- [x] Faire marcher l'application
- [x] Créer un mode d'emploi pour faire marcher l'application (un docker-compose par exemple ?)
- [ ] Trouver les dépendances non maintenu

### Faire marcher l'application
- J'ai d'abord rajouté un service de base de données dans le docker compose.
```yml
db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: mdp
      MYSQL_DATABASE: racoin
    ports:
      - "3306:3306"
```
- J'ai lancé le docker compose et j'ai installé les dépendances à l'intérieur du conteneur php avec "composer install".
- J'ai rajouté un fichier de config "config.ini" dans le dossier de config, avec les infos de configuration de la bd.
```ini
driver=mysql
host=db
username=root
password=mdp
database=racoin
charset=utf8
collation=utf8_unicode_ci
```
- J'ai lancé les différents scripts sql à l'aide de adminer dans la base de données "Racoin"
- J'ai remarqué qu'il manquait une table dans les script d'insertion : "sous_categorie". On peut soit ajouter la table dans le script d'insertion des tables de la bd, soit faire une migration de la base de données.

### Dépendances non maitenues
- La version de PHP 7.4 n'est plus supportée
- Quand on lance la commande "composer outdated", on peut voir toutes les dépendances avec les nouvelles versions possibles.

## Troisième étape - La maintenance
- [ ] Mettre à jour les versions de langages et de framework 
- [ ] Notez dans une TODO list les améliorations que vous avez en tête
- [ ] Pour chaque idée, essayer de noter sur 10 le temps de la modification, et l'impact de la modification (2 notes donc)

### Mettre à jour les dépendances


## Quatrième étape - Vous êtes si rapide ?
- [ ] Faire une liste des améliorations que vous avez faites