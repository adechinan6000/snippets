# Link

```php
<a href="{{ path('welcome') }}">Home</a>

<a href="{{ path('article_show', {'slug': article.slug}) }}">
        {{ article.title }}
</a>
```

# Linking to Assets

```php
// make image folder in web folder
img src="{{ asset('images/logo.png') }}" alt="Symfony!" />

<link href="{{ asset('css/blog.css') }}" rel="stylesheet" />
```