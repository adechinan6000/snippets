# Installing this package

```bash
composer require mashape/unirest-php
```

## Make get request

```php
// search Songs of Frank Sinatra
$headers = array('Accept' => 'application/json');
$query = array('q' => 'Frank sinatra', 'type' => 'track');        
$response = Unirest\Request::get('https://api.spotify.com/v1/search',$headers,$query);
// or use a plain text request
// $response = Unirest\Request::get('https://api.spotify.com/v1/search?q=Frank%20sinatra&type=track');
// Display the result
return $this->json($response->body);
```