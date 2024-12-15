# docs-publications

Bienvenue dans la documentation de `docs-publications`. Ce guide vous expliquera comment configurer et utiliser le système de documentation basé sur GitHub et PHP.

## Table des Matières

1. [Introduction](#introduction)
2. [Prérequis](#prérequis)
3. [Installation](#installation)
4. [Configuration](#configuration)
5. [Utilisation](#utilisation)
6. [Structure des Fichiers](#structure-des-fichiers)
7. [Personnalisation](#personnalisation)
8. [Dépannage](#dépannage)
9. [Contribuer](#contribuer)
10. [Licence](#licence)

## Introduction

`docs-publications` est un système de documentation simple et efficace qui récupère et affiche dynamiquement les fichiers Markdown depuis un dépôt GitHub. Il utilise PHP et la bibliothèque Parsedown pour convertir le Markdown en HTML.

## Prérequis

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un serveur web (Apache, Nginx, etc.)
- PHP 7.4 ou supérieur
- Composer (pour gérer les dépendances PHP)
- Un compte GitHub

## Installation

Suivez ces étapes pour installer le système de documentation :

1. Clonez le dépôt GitHub :

    ```bash
    git clone https://github.com/akirasteam-com/docs-publications.git
    ```

2. Accédez au répertoire du projet :

    ```bash
    cd docs-publications
    ```

3. Installez les dépendances PHP avec Composer :

    ```bash
    composer install
    ```

4. Configurez votre serveur web pour pointer vers le répertoire `docs-publications`.

## Configuration

1. Créez un fichier de configuration `config.php` dans le répertoire [`src`](src ) :

    ```php
    // filepath: /C:/xampp/htdocs/docs-publications/src/config.php
    <?php
    return [
        'site' => [
            'name' => 'Docs.Publications',
            'url' => 'http://localhost/docs-publications',
            'contact_email' => 'contact@akirasteam.com'
        ],
        'repoUrl' => 'https://api.github.com/repos/akirasteam-com/docs-publications/contents/pages'
    ];
    ```

2. Assurez-vous que le fichier `Parsedown.php` est présent dans le répertoire [`src/libs`](src/libs ).

## Utilisation

1. Ajoutez des fichiers Markdown (`.md`) dans le dossier `pages` de votre dépôt GitHub.

2. Accédez à votre site de documentation via votre navigateur web. Par exemple :

    ```
    http://localhost/docs-publications
    ```

3. Utilisez le menu latéral pour naviguer entre les différentes pages de documentation.

## Structure des Fichiers

Voici la structure des fichiers du projet :
```
docs-publications/
├── index.php
├── src/
│ ├── config.php
│ ├── css/
│ │ └── global_style_v2.css
│ └── libs
│ | └── Parsedown.php
└── README.md
```

## Personnalisation

Vous pouvez personnaliser le style et le contenu de la documentation en modifiant les fichiers suivants :

- **CSS** : Modifiez le fichier [global_style_v2.css](http://_vscodecontentref_/1) pour changer le style de la documentation.
- **Configuration** : Modifiez le fichier [`src/config.php`](src/config.php ) pour changer les paramètres du site.
- **Pages** : Ajoutez ou modifiez les fichiers Markdown dans le dossier `pages` de votre dépôt GitHub.

## Dépannage

### Problèmes Courants

1. **Erreur 404** : Assurez-vous que votre serveur web est correctement configuré pour pointer vers le répertoire `docs-publications`.
2. **Problèmes de dépendances** : Assurez-vous d'avoir exécuté `composer install` pour installer les dépendances PHP.

### Logs et Debugging

- Vérifiez les logs de votre serveur web pour des messages d'erreur.
- Utilisez des outils de debugging PHP pour identifier les problèmes.

## Contribuer

Nous accueillons les contributions de la communauté ! Pour contribuer :

1. Forkez le dépôt.
2. Créez une branche pour votre fonctionnalité ou correction de bug.
3. Soumettez une pull request avec une description détaillée de vos changements.

## Licence

Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus de détails.

---

© 2023 AkirasTeam. Tous droits réservés.
