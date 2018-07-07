## Installation

Bow est un micro framework php ivoirien MVC. Ecrit pour les débutants qui veulent travail sur un projet un peut plus
grand. Cette document ce veut simple avec des exemples et les prototypes des fonctions pour vous emmener
à bien comprendre l'outil.

[![GitHub forks](https://img.shields.io/github/forks/papac/bow.svg?label=Fork&style=flat-square)](https://github.com/papac/bow)
[![docs](https://img.shields.io/packagist/v/papac/bow.svg?style=flat-square)](https://packagist.org/papac/bow)
[![Travis branch](https://img.shields.io/travis/papac/framework/master.svg?style=flat-square)](https://travis-ci.com/papac/framework)

* Required
* Getting Started
* Configuration
* Routing
* Controlleurs
* Middlewares
* Vues
* Validator
* Database
* ORM (Maany)
* Mail
* Collection
* Event
* Bow (task runner)
* Helper List
* Extrat

[![GitHub forks](https://img.shields.io/github/forks/papac/bow.svg?label=Fork&style=flat-square)](https://github.com/papac/bow)
[![docs](https://img.shields.io/packagist/v/papac/bow.svg?style=flat-square)](https://packagist.org/papac/bow)
[![Travis branch](https://img.shields.io/travis/papac/framework/master.svg?style=flat-square)](https://travis-ci.com/papac/framework)

## Getting started

### Préréquis

Vous devez vous assurer les différents elements suivants sont installés sur votre machine.

* php >= 7.0
* mcrypt
* mb_string
* PDO
* php-sqlite3 (optionnel) seulement si vous utiliser une db sqlite.
* php-openssl
* php-curl

### Installation

Pour installer une copie de Bow il vous faut d'abort installer [composer](https://getcomposer.org) ensuite vous lancez la commande suivant:

```bash
$ composer create-project --prefer-dist papac/bow
```

### Lancer un test

Vous pouvez tester votre application directement sans serveur web telque `apache` ou `nginx`.
Il vous suffit de vous déplacer dans le dossier de l'application et ensuite lancer la commande qui suit:

```bash
$ php bow serve
```

> Vous pouvez changer le port et le nom d'host avec les options `--host` et `--port`. Par défaut le port est à `5000`.
> et l'host est `localhost`. Si vous voulez faire sortir le serveur de sur le réseau remplacez `localhost` par `0.0.0.0`.
> et aussi ajouter options pour `php` avec `--php-settings=""`. Comme par exemple `-php-settings="-d display_errors=1"`
> ```bash
> $ php bow serve --host=localhost --port=8000
> ```

Enfin ouvrez votre navigateur et entrez l'url correspondant. Chez moi c'est `http://localhost:8000`.

### Ngnix

Pour les utilisateurs de nginx, vous devez ajouter les lignes suivantes à votre configuration.

```nginx
root /path/to/bow/public/;

location / {
	if (!-e $request_filename){
		rewrite ^(.*)$ /index.php break;
	}
}
```