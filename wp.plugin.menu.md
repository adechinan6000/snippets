# Add menu and sub menu plugin 


```php

/* add in __construct() method this: 
     add_action('admin_menu', array($this, 'my_menu_pages'));
*/

function my_menu_pages(){
    add_menu_page('My Page Title', 'My Menu Title', 'manage_options', 'my-menu', array( $this, 'my_menu_output' ) );
    add_submenu_page('my-menu', 'Submenu Page Title', 'Whatever You Wanto', 'manage_options', 'my-menu',  array( $this, 'my_menu_output' ) );
    add_submenu_page('my-menu', 'Submenu Page Title2', 'Whatever You Want2', 'manage_options', 'my-menu2',  array( $this, 'my_menu_output' ) );
}


function my_menu_output() {
     echo 'olla';
}


```