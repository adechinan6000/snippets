# JSON to PHP Using json_decode

## sample 1

```php
$json = '["apple","orange","banana","strawberry"]';
$ar = json_decode($json);
// access first element of $ar array
echo $ar[0]; // apple
```

## sample 2

```php
$json = '{
    "title": "JavaScript: The Definitive Guide",
    "author": "David Flanagan",
    "edition": 6
}';
$book = json_decode($json);
// access title of $book object
echo $book->title; // JavaScript: The Definitive Guide 
```