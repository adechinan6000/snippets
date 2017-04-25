## translation

### Code PHP - Exemple : fr-lang.php 

```bash
<?php
define('TXT_ACCUEIL_INDEX', 'Bienvenue sur PHP Débutant !');
define('TXT_METEO', 'Il fait un soleil radieux !');
define('TXT_CONSEIL_INDEX', 'Faites du PHP !');
?>
```

### Code PHP - Exemple : en-lang.php 

```bash
<?php
define('TXT_ACCUEIL_INDEX', 'Welcome on PHP Débutant !');
define('TXT_METEO', 'The sun is shining !');
define('TXT_CONSEIL_INDEX', 'Let's do some PHP !'); 
?>
```


### Code PHP - Script de Base : decide-lang.php

```bash
<?php	 
if ($_GET['lang']=='fr') {           
    include('lang/fr-lang.php');
} 

else if ($_GET['lang']=='en') {      
    include('lang/en-lang.php');
}
	 
else {                       
    include('lang/fr-lang.php');
}
?>
```

### test

```bash
<?php
require("decide-lang.php");
?>
<html>
<body>
 <?php echo TXT_ACCUEIL_INDEX; ?>
 <br>
Meteo du jour : <?php echo TXT_METEO; ?>
<br>
Conseil du jour : <?php echo TXT_CONSEIL_INDEX; ?>
</body>
</html> 
```