## Paginanation

### Requête

```bash
<?php
$cnx = new PDO('mysql:host=localhost;database=my_database;charset=utf8', 'root', '');
$page = (!empty($_GET['page']) ? $_GET['page'] : 1);
$limite = 10;
// Partie "Requête"
/* On calcule donc le numéro du premier enregistrement */
$debut = ($page - 1) * $limite;
/* On ajoute le marqueur pour spécifier le premier enregistrement */
$query = 'SELECT * FROM `my_table` LIMIT :limite OFFSET :debut';
$query = $cnx->prepare($query);
$query->bindValue('limite', $limite, PDO::PARAM_INT);
/* On lie aussi la valeur */
$query->bindValue('debut', $debut, PDO::PARAM_INT);
$resultSet = $query->execute();

// Partie "Boucle"
while ($element = $resultSet->fetch()) {
    // C'est là qu'on affiche les données  :)
}
?>
```

###Partie "Liens"

```bash
/* Notez que les liens ainsi mis vont bien faire rester sur le même script en passant
 * le numéro de page en paramètre */
?>
<a href="?page=<?php echo $page - 1; ?>">Page précédente</a>
—
<a href="?page=<?php echo $page + 1; ?>">Page suivante</a>
```
