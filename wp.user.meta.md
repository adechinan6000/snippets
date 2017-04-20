# Handling user meta

```php

// see "create user snippet"
// add this code in create user snippet

add_user_meta( $user_id, 'level_of_awesomeness', 15000 );
$data = get_user_meta( $user_id, 'level_of_awesomeness', true );

// update meta data
update_user_meta( $user_id, 'level_of_awesomeness', 15000, 14000 );

```