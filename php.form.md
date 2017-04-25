// MODELE GENERALE FORMULAIRE HTML5

<form id="monForm" action="fichier.php" method="post" autocomplete='off'>
    <label for="pseudo">Pseudo</label>
    <input type="text" id="pseudo" name="pseudo" autocomplete="off" required />
    <input type="submit" id="envoyer" value="Envoyer" />
</form>
------------------------------------------------------

// TRANSMETTRE ET RECUPERER UN PARAMETRE AVEC GET:

href="editform.php?edit_id=<?php echo $row['productID']; ?>" // edit_id est le nom de la variable et peut contenir n'importe quoi


if(isset($_GET['edit_id']) && !empty($_GET['edit_id']))   
{
//		
}
else
{
	header("Location: index.php");
}
http://www.monsite.com/bonjour.php?nom=Dupont&prenom=Jean   ici les variables sont nom et prenom et leur contenu Dupont et jean
<a href="bonjour.php?nom=Dupont&amp;prenom=Jean">Dis-moi bonjour !</a> // dans le code html remplacer & par &amp
$_GET['nom'] // permet de r�cup�rer
isset($_GET['nom']) && !empty($_GET['nom'])// tester si la variable nom existe et si elle contient une valeur
------------------------------------------------------------------------------

// TRANSMETTRE ET RECUPERER AVEC POST:

<form id="monForm" action="fichier.php" method="post">
    <label for="pseudo">Pseudo</label>
    <input type="text" id="pseudo" name="pseudo" autocomplete="off" required />
    <input type="submit" id="envoyer" value="Envoyer" />
</form>


if(isset($_POST['pseudo']) && !empty($_POST['pseudo']))   
{
//		
}
else
{
	header("Location: index.php");
}
----------------------------------------------------------------------------------

// RECUPERER LA VALEUR D'UNE LISTE/ CASE A COCHER / BOUTONS RADIO / CHAMP CACHE
<select name="choix">
<option value="choix1">Choix 1</option>
<option value="choix2">Choix 2</option>
<option value="choix3">Choix 3</option>
<option value="choix4">Choix 4</option>
</select>
 $_POST['choix'] correspondra � ce qui aura �t� coch�: ex choix1
**********************************
<form action="checkbox-form.php" method="post">
    Do you need wheelchair access?
    <input type="checkbox" name="formWheelchair" value="Yes" />
    <input type="submit" name="formSubmit" value="Submit" />
</form>
$_POST['formWheelchair'] == 'Yes'.............
***********************************************
Aimez-vous les frites ?
<input type="radio" name="frites" value="oui" id="oui" checked="checked" /> <label for="oui">Oui</label>
<input type="radio" name="frites" value="non" id="non" /> <label for="non">Non</label>
$_POST['frites']
*******************************************
<input type="hidden" name="pseudo" value="Mateo21" />
$_POST['pseudo'] contiendra Mateo21
----------------------------------------------------------------------------------------


// ENVOYER UN FORMULAIRE A LA PAGE LUI MEME :
* placer en d�but de fichier :

if(isset($_POST['envoyer'])) {   // tester si le bouton envoyer a �t� appuy�
		// suite
}

* s'assurer de la pr�sence de l'attribut "method" et supprimer l'attribut "action" de la balise form:
<form method="post" enctype="multipart/form-data" class="">

* gestion des erreurs et succ�s :
$errMSG = "Svp entrez le nom du produit.";
$successMSG = "Le produit a �t� bien ins�r� dans la base de donn�es...";

* afficher les messages n'importes o� :
 <?php
	if(isset($errMSG)){
			?>
            <div class="alert alert-danger">
            	<span class="glyphicon glyphicon-info-sign"></span> <strong><?php echo $errMSG; ?></strong>
            </div>
            <?php
	}
	else if(isset($successMSG)){
		?>
        <div class="alert alert-success">
              <strong><span class="glyphicon glyphicon-info-sign"></span> <?php echo $successMSG; ?></strong>
        </div>
        <?php
	}
 ?>   
---------------------------------------------------------------------------------------------------------------

// SECURISER LES DONNEES D'UN FORMULAIRE
<?php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>
--------------------------------------------------------------------------------------------------------------------


// UPLOAD SANS RETAILLAGE D'IMAGE
<form action="cible_envoi.php" method="post" enctype="multipart/form-data">
<p>
Formulaire d'envoi de fichier :<br />
<input type="file" name="monfichier" /><br />
<input type="text" name="nom" /><br />
<input type="submit" value="Envoyer le fichier" />
</p>
</form>

<?php
// Testons si le fichier a bien �t� envoy� et s'il n'y a pas d'erreur
if (isset($_FILES['monfichier']) AND $_FILES['monfichier']['error'] == 0)
{
// Testons si le fichier n'est pas trop gros
if ($_FILES['monfichier']['size'] <= 1000000)
	{
// Testons si l'extension est autoris�e
$infosfichier = pathinfo($_FILES['monfichier']['name']);
$extension_upload = $infosfichier['extension'];
$extensions_autorisees = array('jpg', 'jpeg', 'gif', 'png');
if (in_array($extension_upload, $extensions_autorisees))
{
// On peut valider le fichier et le stocker d�finitivement
move_uploaded_file($_FILES['monfichier']['tmp_name'], 'uploads/' . basename($_FILES['monfichier']['name']));
echo "L'envoi a bien �t� effectu� !".$_POST['nom'];
}
}
}
-----------------------------------------------------------------------------------------------------------

// UPLOAD AVEC RETAILLAGE D'IMAGE
<?php
// Testons si le fichier a bien �t� envoy� et s'il n'y a pas d'erreur
if (isset($_FILES['monfichier']) AND $_FILES['monfichier']['error'] == 0)
{
// Testons si le fichier n'est pas trop gros
if ($_FILES['monfichier']['size'] <= 1000000)
	{
// Testons si l'extension est autoris�e
$infosfichier = pathinfo($_FILES['monfichier']['name']);
$extension_upload = $infosfichier['extension'];
$extensions_autorisees = array('jpg', 'jpeg', 'gif', 'png');
if (in_array($extension_upload, $extensions_autorisees))
{
// On peut valider le fichier et le stocker d�finitivement
move_uploaded_file($_FILES['monfichier']['tmp_name'], 'uploads/' . basename($_FILES['monfichier']['name']));

if ($extension_upload == 'jpg') {
	
// Cr�ation de l'image r�duite
$source = imagecreatefromjpeg('uploads/' . basename($_FILES['monfichier']['name'])); // La photo est la source
$destination = imagecreatetruecolor(200, 150); // On cr�e la miniature vide
// Les fonctions imagesx et imagesy renvoient la largeur et la hauteur d'une image
$largeur_source = imagesx($source);
$hauteur_source = imagesy($source);
$largeur_destination = imagesx($destination);
$hauteur_destination = imagesy($destination);
// On cr�e la miniature
imagecopyresampled($destination, $source, 0, 0, 0, 0, $largeur_destination,$hauteur_destination, $largeur_source, $hauteur_source);
// On enregistre la miniature sous le nom voulu
imagejpeg($destination, 'uploads/uploadsbit/' . basename($_FILES['monfichier']['name']));
	
}

echo "L'envoi a bien �t� effectu� !".$_POST['nom'];
}
}
}