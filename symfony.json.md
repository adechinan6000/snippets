# Json

```php
// ...
public function indexAction()
{
    // returns '{"username":"jane.doe"}' and sets the proper Content-Type header
    return $this->json(array('username' => 'jane.doe'));

    // the shortcut defines three optional arguments
    // return $this->json($data, $status = 200, $headers = array(), $context = array());
}
```