# Install your package

```bash
composer require michelf/php-markdown
```

# Before controller

```bash
use \Michelf\Markdown;
```

# In controller method

```php
    /**
     * @Route("/lucky/number")
     */
    public function numberAction()
    {
        $number = mt_rand(0, 100);

        echo Markdown::defaultTransform("#test");
    }
```

# Complete

```php
namespace AppBundle\Controller;

use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;
use Symfony\Component\HttpFoundation\Response;
use \Michelf\Markdown;

class LuckyController
{
    
    /**
     * @Route("/lucky/number")
     */
    public function numberAction()
    {
        $number = mt_rand(0, 100);

        echo Markdown::defaultTransform("#test");
    }
}
```