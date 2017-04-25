## php date


```bash
<?php
$date = date("d-m-Y");
$heure = date("H:i");
Print("Nous sommes le $date et il est $heure");
?>
```



* a - "am" (matin) ou "pm" (après-midi)
* A - "AM" (matin) ou "PM" (après-midi)
* d - Jour du mois, sur deux chiffres (éventuellement avec un zéros) : "01" à "31"
* D - Jour de la semaine, en trois lettres (et en anglais) : par exemple "Fri" (pour Vendredi)
* F - Mois, textuel, version longue; en anglais, i.e. "January" (pour Janvier)
* h - Heure, au format 12h, "01" à "12"
* H - heure, au format 24h, "00" à "23"
* g - Heure, au format 12h sans les zéros initiaux, "1" à "12"
* G - Heure, au format 24h sans les zéros initiaux, "0" à "23"
* i - Minutes; "00" à "59"
* j - Jour du mois sans les zéros initiaux: "1" à "31"
* l - ('L' minuscule) - Jour de la semaine, textuel, version longue; en anglais, i.e. "Friday" (pour Vendredi)
* L - Booléen pour savoir si l'année est bissextile ("1") ou pas ("0")
* m - - Mois; i.e. "01" à "12"
* n - Mois sans les zéros initiaux; i.e. "1" à "12"
* M - Mois, en trois lettres (et en anglais) : par exemple "Jan" (pour Janvier)
* s - Secondes; i.e. "00" à "59"
* S - Suffixe ordinal d'un nom