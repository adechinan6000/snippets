# At same level as src folder

## .htaccess

```bash

RewriteEngine On 
RewriteCond %{REQUEST_FILENAME} !-f 
RewriteCond %{REQUEST_FILENAME} !-d 
RewriteRule ^(.*)$ web/$1

```

## run this

```bash

php bin/console cache:clear --env=prod

```