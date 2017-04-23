# Create custom Repository Classes

* entitie

```bash
// src/AppBundle/Entity/Product.php
namespace AppBundle\Entity;

use Doctrine\ORM\Mapping as ORM;

/**
 * @ORM\Entity(repositoryClass="AppBundle\Repository\ProductRepository")
 */
class Product
{
    //...
}
```

* repository

```bash
// src/AppBundle/Repository/ProductRepository.php
namespace AppBundle\Repository;

use Doctrine\ORM\EntityRepository;

class ProductRepository extends EntityRepository
{
    public function findAllOrderedByName()
    {
        return $this->getEntityManager()
            ->createQuery(
                'SELECT p FROM AppBundle:Product p ORDER BY p.name ASC'
            )
            ->getResult();
    }
}
```

* controller

```bash
$em = $this->getDoctrine()->getManager();
$products = $em->getRepository('AppBundle:Product')
    ->findAllOrderedByName();
```