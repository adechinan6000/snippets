# Session

### Start session before (everything)

```bash
<?php
session_start() ;
if(empty($_SESSION))session_start();  // on peut vérifier avant
?>
```

### Adding into session

```bash
$_SESSION['login'] = $_POST['login'];
```

### Checking into session

```bash
if (isset($_SESSION['login']) && isset($_SESSION['pwd'])) {....}
```


### Destroy session

```bash
session_destroy();
```