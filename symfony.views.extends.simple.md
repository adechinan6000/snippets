# Inheritance simple
## Base

```php
{# app/Resources/views/blog/layout.html.twig #}
{% extends 'base.html.twig' %}

{% block body %}
    <h1>Blog Application</h1>

    {% block content %}{% endblock %}
{% endblock %}
```

## Child

```php
{# app/Resources/views/blog/index.html.twig #}
{% extends 'blog/layout.html.twig' %}

{% block content %}
    {% for entry in blog_entries %}
        <h2>{{ entry.title }}</h2>
        <p>{{ entry.body }}</p>
    {% endfor %}
{% endblock %}
```