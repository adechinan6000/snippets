### Send mail

* composer dependencies

```bash
composer require phpmailer/phpmailer
```

* sample 1

```bash
<?php
require 'PHPMailerAutoload.php';

$mail = new PHPMailer();
$mail->isSMTP();                                     
$mail->IsSMTP();
$mail->SMTPAuth = true;
$mail->Username = "atsk1618@gmail.com";
$mail->Password = "1984sunsetboulevard";
$mail->SMTPSecure = "ssl";  
$mail->Host = "smtp.gmail.com";
 $mail->Port = "465";

$mail->setFrom('atsk1618@gmail.com', 'Adechinan');
$mail->addAddress('adechinan6000@gmail.com', 'Adechinan');     // Add a recipient, name is optional
$mail->AddCC('zansouye.dossou@gmail.com');				// second recipient
//$mail->AddCC('person2@domain.com');             // third recipient



$mail->isHTML(true);                                  // Set email format to HTML
$mail->Subject = 'Here is the subject';
$mail->Body    = 'This is the HTML message body <b>in bold!</b>';
$mail->AltBody = 'This is the body in plain text for non-HTML mail clients';

if(!$mail->send()) {
    echo 'Message could not be sent.';
    echo 'Mailer Error: ' . $mail->ErrorInfo;
} else {
    echo 'Message has been sent';
}
```

* sample 2

```bash
<?php
require 'PHPMailerAutoload.php';

$mail = new PHPMailer();

//$mail->SMTPDebug = 3;                               // Enable verbose debug output

$mail->isSMTP();                                      // Set mailer to use SMTP
$mail->Host = 'smtp1.example.com;smtp2.example.com';  // Specify main and backup SMTP servers
$mail->SMTPAuth = true;                               // Enable SMTP authentication
$mail->Username = 'user@example.com';                 // SMTP username
$mail->Password = 'secret';                           // SMTP password
$mail->SMTPSecure = 'tls';                            // Enable TLS encryption, `ssl` also accepted
$mail->Port = 587;                                    // TCP port to connect to

$mail->setFrom('from@example.com', 'Mailer');
$mail->addAddress('joe@example.net', 'Joe User');     // Add a recipient
$mail->addAddress('ellen@example.com');               // Name is optional
$mail->addReplyTo('info@example.com', 'Information');
$mail->addCC('cc@example.com');
$mail->addBCC('bcc@example.com');

$mail->addAttachment('/var/tmp/file.tar.gz');         // Add attachments
$mail->addAttachment('/tmp/image.jpg', 'new.jpg');    // Optional name
$mail->isHTML(true);                                  // Set email format to HTML

$mail->Subject = 'Here is the subject';
$mail->Body    = 'This is the HTML message body <b>in bold!</b>';
$mail->AltBody = 'This is the body in plain text for non-HTML mail clients';

if(!$mail->send()) {
    echo 'Message could not be sent.';
    echo 'Mailer Error: ' . $mail->ErrorInfo;
} else {
    echo 'Message has been sent';
}
```