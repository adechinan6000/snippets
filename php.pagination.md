## Paginanation

### Requ�te

```bash
<?php
$cnx = new PDO('mysql:host=localhost;database=my_database;charset=utf8', 'root', '');
$page = (!empty($_GET['page']) ? $_GET['page'] : 1);
$limite = 10;
// Partie "Requ�te"
/* On calcule donc le num�ro du premier enregistrement */
$debut = ($page - 1) * $limite;
/* On ajoute le marqueur pour sp�cifier le premier enregistrement */
$query = 'SELECT * FROM `my_table` LIMIT :limite OFFSET :debut';
$query = $cnx->prepare($query);
$query->bindValue('limite', $limite, PDO::PARAM_INT);
/* On lie aussi la valeur */
$query->bindValue('debut', $debut, PDO::PARAM_INT);
$resultSet = $query->execute();

// Partie "Boucle"
while ($element = $resultSet->fetch()) {
    // C'est l� qu'on affiche les donn�es  :)
}
?>
```

###Partie "Liens"

```bash
/* Notez que les liens ainsi mis vont bien faire rester sur le m�me script en passant
 * le num�ro de page en param�tre */
?>
<a href="?page=<?php echo $page - 1; ?>">Page pr�c�dente</a>
�
<a href="?page=<?php echo $page + 1; ?>">Page suivante</a>
```
