## try-catch

```bash
try {
    echo inverse(5) . "\n";
} catch (Exception $e) {
    echo 'Exception reçue : ',  $e->getMessage(), "\n";
}
```






## Error global


```bash
// DESACTIVER LES ERREURS
// During production
ini_set('display_errors','0');

// During development
ini_set('log_errors','1');

// Turn off error reporting
error_reporting(0);

// Report runtime errors
error_reporting(E_ERROR | E_WARNING | E_PARSE);

// Report all errors
error_reporting(E_ALL);

// Same as error_reporting(E_ALL);
ini_set("error_reporting", E_ALL);

// Report all errors except E_NOTICE
error_reporting(E_ALL & ~E_NOTICE);
```