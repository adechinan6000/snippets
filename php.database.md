// connection: 
$DB_HOST = 'localhost';
 $DB_USER = 'root';
 $DB_PASS = '';
 $DB_NAME = 'nambiweproducts';
 
 try{
  $DB_con = new PDO("mysql:host={$DB_HOST};dbname={$DB_NAME}",$DB_USER,$DB_PASS);
  $DB_con->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
 }
 catch(PDOException $e){
  echo $e->getMessage();
 }
---------------------------------------------------------------------------------------
// Créer une table
CREATE TABLE IF NOT EXISTS `tbl_categories` (
  `cat_id` int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY,
  `cat_name` varchar(20) NOT NULL
) ENGINE=MyISAM ;
-------------------------------------------------------------------------------------------

// handle table name dinamically
$query = "SELECT HEAD,DESCRIPTION FROM $table_name ";

// insérer
$stmt = $DB_con->prepare("INSERT INTO nomdelatable (name, value) VALUES (?, ?)");
$stmt->execute([$nom, $age])
--------------------------------------------------------------------------------------------

// récupérer et afficher si résultats beaucoup
$stmt = $DB_con->prepare('SELECT * FROM users WHERE email = ? AND status=?');
$stmt->execute([$email, $status]);

  * teste s'il y a des réponses
  * on les convertit en tableau
  * on appelle les clés pour afficher les valeurs

if($stmt->rowCount() > 0)
	{
		while($row=$stmt->fetch(PDO::FETCH_ASSOC))
		{
			extract($row);

			<?php echo $row['email']; ?> // ici pimg est le nom d'un champ de la table en bd
----------------------------------------------------------------------------------------------------------

// récupérer et afficher si résultat unique
$stmt = $DB_con->prepare("SELECT user_name,user_email FROM users WHERE user_name=:uname OR user_email=:umail");
$stmt->execute(array(':uname'=>$uname, ':umail'=>$umail));
$row=$stmt->fetch(PDO::FETCH_ASSOC);
if($row['user_name']==$uname) {
    $error[] = "sorry username already taken !";
}
---------------------------------------------------------------------------------------------------------

// recherche textuelle
$search = "%$search%";
$stmt  = $DB_con->prepare("SELECT * FROM table WHERE name LIKE ?");
$stmt->execute([$search]);
---------------------------------------------------------------------------------------------------------

// mise à jour
$stmt = $DB_con->prepare("UPDATE users SET name = ? WHERE id = ?");
$stmt->execute([$nom, $age])
-----------------------------------------------------------------------------------------------------------

// delete
$stmt = $DB_con->prepare("DELETE FROM goods WHERE category = ?");
$stmt->execute([$cat]);
----------------------------------------------------------------------------------------------------------

// ORDER_BY
$stmt  = $DB_con->prepare("SELECT * FROM products WHERE name LIKE ? ORDER BY price ASC"); 
$stmt->execute([$search]); // ASC: du plus petit au plus grand; DESC: inverse
--------------------------------------------------------------------------------------------------------

// MIN MAX
$stmt2  = $DB_con->prepare("SELECT MIN(price) FROM products"); // SELECT MIN(column_name) FROM table_name;
$stmt2->execute();
$min = $stmt2->fetchColumn();
echo $min // déjà convertit en int
--------------------------------------------------------------------------------------------------------

// jointure
CREATE TABLE IF NOT EXISTS `tbl_categories` (
  `cat_id` int(5) NOT NULL AUTO_INCREMENT,
  `cat_name` varchar(20) NOT NULL,
  PRIMARY KEY (`cat_id`)
) ENGINE=MyISAM  DEFAULT CHARSET=latin1 AUTO_INCREMENT=5 ;
INSERT INTO `tbl_categories` (`cat_id`, `cat_name`) VALUES
(1, 'samsung'),
(2, 'nokia'),
(3, 'htc');
CREATE TABLE IF NOT EXISTS `tbl_products` (
  `product_id` int(5) NOT NULL AUTO_INCREMENT,
  `product_name` varchar(30) NOT NULL,
  `cat_id` int(5) NOT NULL,
  PRIMARY KEY (`product_id`)
) ENGINE=MyISAM  DEFAULT CHARSET=latin1 AUTO_INCREMENT=7 ;
INSERT INTO `tbl_products` (`product_id`, `product_name`, `cat_id`) VALUES
(1, 'galaxy note', 1),
(3, 'lumia 530', 2),
(5, 'htc grid', 3);

SELECT tbl_a.column1 , tbl_a.column2
       tbl_b.column1 , tbl_b.column2
FROM   tbl_a INNER JOIN tbl_b
ON     tbl_a.commonfield=tbl_b.commonfield
---------------------------------------------------------------


// AUTRE SYNTAXE
$search = "%$query%";
$stmt  = $DB_con->prepare("SELECT * FROM products  WHERE name LIKE ? ORDER BY price ASC LIMIT ? OFFSET 2");
$stmt->bindValue(1, $search, PDO::PARAM_STR);
$stmt->bindValue(2, $again, PDO::PARAM_INT);
$stmt->execute();