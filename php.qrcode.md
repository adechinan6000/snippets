## Setup

* composer

```bash
composer require arcanedev/qr-code
composer require khanamiryan/qrcode-detector-decoder
```

## Create, Read, Check

* usage

```bash
require_once 'vendor/autoload.php';
use Arcanedev\QrCode\QrCode;

$qrCode = new QrCode;
$qrCode->setText("I would love to change the world");
$qrCode->setSize(200);
echo $qrCode->image("image alt", ['class' => 'qr-code-img']);


$qrcode = new QrReader('qr.png');
$text = $qrcode->text(); //return decoded text from QR Code
echo $text;


if ($qrCode->getText() == $text) echo "true";
```
