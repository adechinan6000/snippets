# Add class for autoload


## Put the classes that we want to autoload in a dedicated directory

```bash
your-website/
  src/
    Db.php
    User.php
    Pages/
      Page.php
```

## Give the classes a namespace

```php
<?php
namespace Acme\Pages; // namespace Acme for others (db, users)

public class Page {
    function __construct()
    {
        echo "hello, i am a page.";
    }
}
```

## Point the namespace to the src/ directory in the composer.json file

```bash
{
  "autoload": {
    "psr-4": {
      "Acme\\":"src/"
    }
  }
}

```

## Use it

```php
<?php 
<?php
require "vendor/autoload.php";

use Acme\Db;
use Acme\User;
use Acme\Pages\Page;


$page1 = new Page();
```