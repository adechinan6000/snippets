# Create reusable bundle

* Créer un projet Symfony

```bash
php composer.phar create-project symfony/framework-standard-edition /repertoire/du/projet
```

* Créer un bundle (votre futur package)

```bash
php app/console generate:bundle
cd src/MonNom/TestBundle/
```

* Initialiser Git

```bash
git init
git add .
git commit -m "premier commit"
git remote add origin {votre dépot git}
git push -u origin master
```

* Ce qui fait la différence: créer le fichier composer.json à la racine de votre bundle

```bash
{
    "name" : "monnom/testbundle",
    "description" : "C'est mon bundle",
    "type" : "symfony-bundle",
    "authors" : [{
        "name" : "test",
        "email" : "monnom@mondomaine.com"
    }],
    "keywords" : [
        "test bundle"
    ],
    "require" : {
            "php" : ">=5.5.0",
            "symfony/framework-bundle" : ">=2.5.6",
            "twig/twig" : "*",
            "doctrine/doctrine-bundle" : "*"
    },
    "autoload" : {
        "psr-0" : {
            "MonNom\\TestBundle" : ""
        }
    },
    "target-dir" : "MonNom/TestBundle",
}
```

* Développer votre bundle