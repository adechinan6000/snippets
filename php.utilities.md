## utilities


```bash
// PHP TAG
<?php .... ?>
-----------------------------------------------------

// INCLURE DE N'IMPORTE OU
include $_SERVER['DOCUMENT_ROOT']."/nambiwe/backend/dbconfig.php"; // nambiwe est le dossier racine
-----------------------------------------------------------

// ENCODER EN UTF-8
echo utf8_encode($row['catname'])
-------------------------------------------------------

// DEFINE CONSTANT
define('DB_SERVER','localhost');
----------------------------------------------

// CONCATENATION
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
----------------------------------------------

// INCLUDE
require_once 'class.user.php';
require_once('dossier/script.php');
----------------------------------------------



// TABLEAU
$cars=array("Volvo","BMW","Toyota");
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
foreach ($cars as $car) {
    echo "Aimez-vous la marque $car ?\n";
}

$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");

foreach($age as $x=>$x_value)
  {
  echo "Key=" . $x . ", Value=" . $x_value;
  echo "<br>";
  }
?> 

$cars=array
  (
  array("Volvo",100,96),
  array("BMW",60,59),
  array("Toyota",110,100)
  );
echo $cars[0][0].": Ordered: ".$cars[0][1].". Sold: ".$cars[0][2]."<br>";
echo $cars[1][0].": Ordered: ".$cars[1][1].". Sold: ".$cars[1][2]."<br>";
echo $cars[2][0].": Ordered: ".$cars[2][1].". Sold: ".$cars[2][2]."<br>";
---------------------------------------------------------------------

// MIXING HTML AND PHP
$name = 'joe';
echo <<<FOOBAR
<div id ="footer">
printed by alvin $name, {$_SESSION['login']}
<br/>devdaily.com
</div>
FOOBAR;
-------------------------------------------------------------------

// MIXING PHP AND JAVASCRIPT (doit se faire sur la même page)
?>
    <script>
	alert('Mise à jour réussi...');
	window.location.href='index.php';
    </script>
<?php
--------------------------------------------------------------------

// REDIRECT
header("Location: index.php");
header("refresh:5;index.php"); // redirects image view page after 5 seconds.
window.location.href='index.php'; // en javascript dans certains cas.(après une mise à jour en BD)
sign-up.php?joined // rediriger sur la page d'inscription après inscription
if(isset($_GET['joined'])) {..// et afficher message succès ..// }
$fname   = $_GET['name'];
$femail  = $_GET['email'];
$fphone  = $_GET['telephone'];
//now a header with these var's:
header("Location: confirmed.php?name=".$fname."&email=".$femail."&telephone=".$fphone);
header("Location: comparis.php?query=$where&pic");
header('Location: http://www.example.com/');
header("Location: /foo.php");
header("Location: http://www.yourwebsite.com/user.php"); /* Redirect browser */
exit(); // It is a good practice to call exit() right afterwords so that code below it does not get executed.
---------------------------------------------------------------------------------------------------



// INCLURE TOUS LES FICHIERS D'UN DOSSIER
foreach (glob("path/to/css/*.css") as $css) {
    echo "<link type='text/css' rel='stylesheet' href='$css'>\n";
}

foreach (glob("classes/*.php") as $filename)
{
    include $filename;
}


```