## Security

## password

```bash
// sha256 : nom de l'algo de hashage
$password = hash("sha256", $password);
$password = md5($upass); if($userRow['userPass']==md5($upass))
```

## display

```bash
trim($_POST['txtuname']); strip_tags($_POST['full_name']); htmlspecialchars($_POST['full_name']);
```

## better hashing

```bash
define("MAX_LENGTH", 6);

function generateHashWithSalt($password) {
    $intermediateSalt = md5(uniqid(rand(), true));
    $salt = substr($intermediateSalt, 0, MAX_LENGTH);
    return hash("sha256", $password . $salt);
}
```

## form spoffing

```bash
$secret = md5(uniqid(rand(), true));
$_SESSION['secret'] = $secret;

<input type="hidden" name="secret" value="<? echo $secret; ?>" />
```