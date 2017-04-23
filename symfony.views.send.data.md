# Views php code

```php
// src/AppBundle/Controller/LuckyController.php
namespace AppBundle\Controller;
use Symfony\Bundle\FrameworkBundle\Controller\Controller;
use Sensio\Bundle\FrameworkExtraBundle\Configuration\Route;

// ...
class LuckyController extends Controller
{
    /**
     * @Route("/lucky/number")
     */
    public function numberAction()
    {
        $number = mt_rand(0, 100);
        
        // bundlename + folder + namefile
        // default for controller name
        return $this->render('MyBundle:Default:index.html.twig');
        return $this->render('MyBundle:Default:number.html.twig', array(
            'number' => $number,
        ));
        
        // simple
        // app/ressource/default/in...
        // default for controller name
        return $this->render('default/index.html.twig'); 
    }
}
```

# view twig code


```php

{# comment: app/Resources/views/lucky/number.html.twig #}
<h1>Your lucky number is {{ number }}</h1>

```