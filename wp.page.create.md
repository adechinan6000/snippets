# Page create auto

```php

function create_page() {
	$my_post1 = array(
		'post_type'    => 'page',
		'post_title'   => 'Add Tester',
		'post_content' => '[add_tester_form]',
		'post_status'  => 'publish',
		'post_author'  => get_current_user_id(),
	);
	wp_insert_post($my_post1);
}

/*
add this to __construct() method:
register_activation_hook( __FILE__, array($this, 'create_page' ));
*/

```