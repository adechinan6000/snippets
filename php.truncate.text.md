## Truncate

### sample 1

```bash
echo substr("Hello world",0,10)."<br>";
```

### sample 2

* Retourne la chaîne tronquée.
* string - La chaîne d'entrée.
* max_length - Longueur maximale de la chaine retournée.
* replacement - Texte de remplacement.
* trunc_at_space - Si ce paramètre vaut TRUE, truncate() tentera de ne pas tronquer la chaine au milieu d'un mot.


```
function truncate($string, $max_length = 30, $replacement = '', $trunc_at_space = false)
{
	$max_length -= strlen($replacement);
	$string_length = strlen($string);
	if($string_length <= $max_length)
		return $string;
	if( $trunc_at_space && ($space_position = strrpos($string, ' ', $max_length-$string_length)) )
		$max_length = $space_position;
	return substr_replace($string, $replacement, $max_length);
}
```

```bash
$str = "Suspendisse at magna non lectus lacinia gravida.";
$str = truncate($str, 40, '...', true);
echo $str; // Suspendisse at magna non lectus...
```