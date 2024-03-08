# Projet 14 - Application Symfony présentée lors de ma soutenance DWWM

## Prérequis

Avant de commencer l'installation de l'application, assurez-vous de disposer des éléments suivants sur votre
environnement de développement :

- PHP >= 7.4
- Composer installé
- MySQL ou un autre système de gestion de base de données supporté par Symfony

## Configuration

1. **Création du fichier .env.local**

   Dupliquez le fichier `.env` que vous nommerez `.env.local` à la racine de votre projet. Assurez-vous de ne conserver
   que les informations essentielles, notamment celles liées à la base de données.

2. **Configuration de la base de données**

   Ouvrez le fichier `.env.local` nouvellement créé et renseignez les informations de votre base de données, en
   particulier la ligne correspondant à la connexion à la base de données.

   Exemple :
   ```dotenv
   DATABASE_URL=mysql://user:password@127.0.0.1:3306/projet14?serverVersion=mariadb-10.3.25&charset=utf8mb4"


## Installation

1. **Installation des dépendances**

Exécutez la commande suivante pour installer les dépendances du projet. Assurez-vous de ne pas exécuter la commande
composer update.

```bash
composer install
```

1. **Création de la base de données**

Utilisez la commande Symfony pour créer la base de données.

```bash
php bin/console doctrine:database:create
```

3. **Import des migrations**

Appliquez les migrations existantes pour créer les tables de la base de données.

```bash
php bin/console doctrine:migrations:migrate
```

4. **Import des fixtures (si existantes)**

Si des fixtures sont disponibles, utilisez la commande suivante pour les charger dans la base de données.

```bash
php bin/console doctrine:fixtures:load
```

## Maintenance

**Génération des clés du jeton JWT**

Si nécessaire, vous pouvez régénérer les clés du jeton JWT en utilisant la commande suivante.

```bash
php bin/console lexik:jwt:generate-keypair
```

## Erreur possible

### Erreur lors de la migration

Si vous rencontrez une erreur lors de la migration, vous pouvez essayer de supprimer le dossier `migrations` dans le
dossier `src` et de le recréer avec la commande suivante ou exécuter les commandes suivantes pour suprimmer la
migration.

```bash
rm -rf migrations/*.php
```

Et créer une nouvelle migration.

```bash
php bin/console make:migration
```

Reprennez le processus à l'étape 3.

### Problème de cache

```bash
php bin/console cache:clear
```

## Réalisé par :
* Axel SANSON - [https://axel-sanson.fr/](https://axel-sanson.fr/)
* Description du projet : [https://axel-sanson.fr/work/projet-14/](https://axel-sanson.fr/work/projet-14/)

#
****English version :****
# Projet 14 - Symfony application presented during my DWWM defense

## Prerequisites

Before starting the installation of the application, ensure that you have the following on your development environment:

- PHP >= 7.4
- Composer installed
- MySQL or another supported database management system

## Configuration

1. **Create the .env.local file**

   Duplicate the `.env` file as `.env.local` at the root of your project. Make sure to keep only the essential
   information, especially those related to the database.

2. **Database Configuration**

   Open the newly created `.env.local` file and fill in the database information, especially the line corresponding to
   the database connection.

   Example:
   ```dotenv
   DATABASE_URL=mysql://user:password@127.0.0.1:3306/projet14?serverVersion=mariadb-10.3.25&charset=utf8mb4"

`

## Installation

1. **Install dependencies**
Execute the following command to install the project dependencies. Make sure not to run the composer update command.

```bash
composer install
```

2. **Create the database**
Use the Symfony command to create the database.

```bash
php bin/console doctrine:database:create
```

3. **Import migrations**
Apply the existing migrations to create the database tables.

```bash
php bin/console doctrine:migrations:migrate
```

4. **Import fixtures**
If fixtures are available, use the following command to load them into the database.

```bash
php bin/console doctrine:fixtures:load
```

## Maintenance

**Generate JWT token keys**
If necessary, you can regenerate the JWT token keys using the following command.

```bash
php bin/console lexik:jwt:generate-keypair
```

## Possible error

### Error during migration
If you encounter an error during migration, you can try to delete the `migrations` folder in the `src` folder and recreate
it with the following command or execute the following commands to delete the migration.

```bash
rm -rf migrations/*.php
```

And create a new migration.

```bash
php bin/console make:migration
```

Resume the process at step 3.

### Cache problem

```bash
php bin/console cache:clear
```

## Made by:

* Axel SANSON - [https://axel-sanson.fr/](https://axel-sanson.fr/)
* Project description : [https://axel-sanson.fr/work/projet-14/](https://axel-sanson.fr/work/projet-14/)
