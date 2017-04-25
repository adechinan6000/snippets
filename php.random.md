## Random

* number

```bash
echo rand(5, 15);
```


* string

```bash
PHP 5.6
$string = bin2hex(openssl_random_pseudo_bytes(10));

In PHP 7 (random_bytes()):
$string = base64_encode(random_bytes(10)); // about 14 chars
// or
$string = bin2hex(random_bytes(10)); // 20 chars
```

* unique id

```bash
uniqid(time(), true);
```