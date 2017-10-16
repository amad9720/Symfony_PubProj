#PUB-ROJ (SYMFONY -- PHP FRAMEWORK)
## 1. Telecharger le projet 
En clone ou en ZIP

## 2. Définir vos paramètres d'application
Pour ne pas qu'on se partage tous nos mots de passe, le fichier `app/config/parameters.yml` est ignoré dans ce dépôt. A la place, vous avez le fichier `parameters.yml.dist` que vous devez renommer (enlevez le `.dist`) et modifier.

## 3. Télécharger les vendors
Avec Composer bien évidemment :

    php composer.phar install

## 4. Créez la base de données
Si la base de données que vous avez renseignée dans l'étape 2 n'existe pas déjà, créez-la :

    php app/console doctrine:database:create

Puis créez les tables correspondantes au schéma Doctrine :

    php app/console doctrine:schema:update --dump-sql
    php app/console doctrine:schema:update --force

Enfin, éventuellement, ajoutez les fixtures :

    php app/console doctrine:fixtures:load

## 5. Publiez les assets
Publiez les assets dans le répertoire web :

    php app/console assets:install web

## Et profitez !
