# Single command

```bash
php bin/console generate:bundle --namespace=Acme/TestBundle
```

# Bundle structure
* Controller/ Contains the controllers (e.g. RandomController.php).
* DependencyInjection/
* Resources/config/
* Resources/views/
* Resources/public/
* Tests/
<your-bundle>/
├─ AcmeBlogBundle.php
├─ Controller/
├─ README.md
├─ LICENSE
├─ Resources/
│   ├─ config/
│   ├─ doc/
│   │  └─ index.rst
│   ├─ translations/
│   ├─ views/
│   └─ public/
└─ Tests/
