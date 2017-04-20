## Enable and configure 

```php
# app/config/config.yml
framework:
    translator: { fallbacks: [en] }
```

## Add message (app/Resources/translations)

```php
# messages.fr.yml
Symfony is great: J'aime Symfony
```

## Clear cache

```bash
php bin/console cache:clear
```

## Use

```php
use Symfony\Component\HttpFoundation\Response;
// When this code is executed, Symfony will attempt to translate the message //"Symfony is great" based on the locale

public function indexAction()
{
    $translated = $this->get('translator')->trans('Symfony is great');

    return new Response($translated);
}
```