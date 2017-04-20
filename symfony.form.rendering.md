# Rendering form

```php
{# app/Resources/views/default/new.html.twig #}
{{ form_start(form) }}
{{ form_widget(form) }}
{{ form_end(form) }}
```

```php
{# renders all fields *and* the form start and end tags #}
{{ form(form) }}
```

```php
{{ form_widget(form.name, { 'attr': {'class': 'foo'} }) }}
```

```php
{# app/Resources/views/default/new.html.twig #}
{{ form_start(form) }}
    {{ form_errors(form) }}

    {{ form_row(form.task) }}
    {{ form_row(form.dueDate) }}
{{ form_end(form) }}
```

```php
{{ form(form, {'attr': {'novalidate': 'novalidate'}}) }}
```