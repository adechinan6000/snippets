# Send mail

```php


// assumes $to, $subject, $message have already been defined earlier...
 
$headers[] = 'From: Me Myself <me@example.net>';
$headers[] = 'Cc: John Q Codex <jqc@wordpress.org>';
$headers[] = 'Cc: iluvwp@wordpress.org'; // note you can just use a simple email address
 
wp_mail( $to, $subject, $message, $headers );


```