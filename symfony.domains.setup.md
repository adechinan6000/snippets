# Db
## Setting 1
```bash
# app/config/parameters.yml
parameters:
    database_host:     localhost
    database_name:     test_project
    database_user:     root
    database_password: password

# ...
```

## Setting 2 (my.cnf)

```bash
[mysqld]
# Version 5.5.3 introduced "utf8mb4", which is recommended
collation-server     = utf8mb4_general_ci # Replaces utf8_general_ci
character-set-server = utf8mb4            # Replaces utf8
```

## Create

```bash
php bin/console doctrine:database:create
```

## Update db

```bash
php bin/console doctrine:schema:update --force
```

## Update after adding new propeties
```bash
php bin/console doctrine:generate:entities AppBundle
```