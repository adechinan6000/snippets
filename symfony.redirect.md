# Redirection

```php
public function indexAction()
{
    // redirect to the "homepage" route
    return $this->redirectToRoute('homepage');

    // do a permanent - 301 redirect
    return $this->redirectToRoute('homepage', array(), 301);

    // redirect to a route with parameters
    return $this->redirectToRoute('blog_show', array('slug' => 'my-page'));

    // redirect externally
    return $this->redirect('http://symfony.com/doc');
}
```