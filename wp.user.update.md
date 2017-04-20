# Update user

```php

function edit_user() {
    wp_update_user(
			array(
				'ID' => get_current_user_id(),
				'nickname' => 'buna.com'
			)
	);
}

```