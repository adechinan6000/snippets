```php
public function showAction($productId)
{
    $product = $this->getDoctrine()
        ->getRepository('AppBundle:Product')
        ->find($productId);

    $categoryName = $product->getCategory()->getName();

    // ...
}
```


```php
public function showProductsAction($categoryId)
{
    $category = $this->getDoctrine()
        ->getRepository('AppBundle:Category')
        ->find($categoryId);

    $products = $category->getProducts();

    // ...
}
```

