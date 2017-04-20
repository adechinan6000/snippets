# Create user

```php

function create_user() {

    $username = $_POST['username'];
	$email_address = $_POST['email'];
	$password      = $_POST['password'];

	if ( null == username_exists( $email_address ) ) {

		$user_id = wp_create_user( $username, $password, $email_address );
		$user    = new WP_User( $user_id );
		$user->set_role( 'tester' );
		echo 'successful created',
	    die();

	}
	
}

```
