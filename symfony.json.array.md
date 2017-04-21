# Symfony json to array for twig

```php
$json = '{
    	"title": "JavaScript: The Definitive Guide",
    	author": "David Flanagan",
    	"edition": 6
		}';
$jsontoarray = json_decode($json, true);
return $this->render('AtskMeBundle:Default:index.html.twig', $jsontoarray);
```