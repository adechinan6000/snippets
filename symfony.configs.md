# Parameters

## Create

```bash
# app/config/config.yml

# ...
parameters:
    brochures_directory: '%kernel.root_dir%/../web/uploads/brochures'
```

## Retrieve

```php
$this->getParameter('brochures_directory');
```