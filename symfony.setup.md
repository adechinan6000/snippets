##  create symfony app
```bash
composer create-project symfony/symfony mava/
```

## run built in server (http://localhost:8000)
```bash
php bin/console server:run
```

## accesing route
```bash
http://localhost:8000/my
```

## for deployment add .htaccess same level as src folder
```bash
RewriteEngine On 
RewriteCond %{REQUEST_FILENAME} !-f 
RewriteCond %{REQUEST_FILENAME} !-d 
RewriteRule ^(.*)$ web/$1
```

## for deployment run this 
```bash
php bin/console cache:clear --env=prod
```