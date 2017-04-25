## pdf

* composer

```bash
composer require sun/pdf
```

* sample

```bash
require_once 'vendor/autoload.php';

$pdf = new Sun\PDF;
$pdf->download("<h1>Hello world</h1>");
```