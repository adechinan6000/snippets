# Display data

* single
```php
{# comment: app/Resources/views/lucky/number.html.twig #}
<h1>Your lucky number is {{ number }}</h1>
```

* loop
```php
<ul>
    {% for user in users if user.active %}
        <li>{{ user.username }}</li>
    {% else %}
        <li>No users found</li>
    {% endfor %}
</ul>
```

* no escaping
```php
{{ article.body|raw }}
```


# Call php 

