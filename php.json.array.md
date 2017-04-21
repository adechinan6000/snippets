# Convert JSON String to PHP Array

## sample 1

```php
// $json same as example object above
// pass true to convert objects to associative arrays
$book = json_decode($json, true);
// access title of $book array
echo $book['title']; // JavaScript: The Definitive Guide
```

##☺ sample 2

```php
$json = '[
    {
        "title": "Professional JavaScript",
        "author": "Nicholas C. Zakas"
    },
    {
        "title": "JavaScript: The Definitive Guide",
        "author": "David Flanagan"
    },
    {
        "title": "High Performance JavaScript",
        "author": "Nicholas C. Zakas"
    }
]';

$books = json_decode($json);
// access property of object in array
echo $books[1]->title; // JavaScript: The Definitive Guide

// $json same as example object above
// pass true to convert objects to associative arrays
$books = json_decode($json, true);
// numeric/associative array access
echo $books[1]['title']; // JavaScript: The Definitive Guide
```