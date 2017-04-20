# Display data

```php
<ul>
    {% for user in users if user.active %}
        <li>{{ user.username }}</li>
    {% else %}
        <li>No users found</li>
    {% endfor %}
</ul>
```

# Do not Escape data

```php
{{ article.body|raw }}
```


# Call php 

