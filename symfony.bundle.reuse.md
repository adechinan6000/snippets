# Reuse bundle

* Ajout ces lignes dans le composer.phar à la racine de votre application Symfony

```bash
 [...]
    "require" : {
        [...]
        "monnom/testbundle" : "dev-master"
    },
 [...]
    "repositories" : [{
        "type" : "vcs",
        "url" : { url de votre dépot git }
    }],
[...]
```

* Lancer cette commande dans le terminal:

```bash
php composer.phar update monnom/testbundle
```

* Ajouter votre bundle dans l’AppKernel.php

```bash
new MonNom\TestBundle\MonNomTestBundle(),
```

* Ajouter les routes si besoin

* Enjoy