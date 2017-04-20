# Plugin option

## 1 - Create Custom Global Settings
```php
function custom_settings_page() {
	?>
  <div class="wrap">
    <h1>Custom Settings</h1>
    <form method="post" action="options.php">
       <?php
	settings_fields ( 'section' );
	do_settings_sections ( 'theme-options' );
	submit_button ();
	?>          
    </form>
  </div>
<?php
}
```

## 2 - Adding setting form
```php
// Twitter
function setting_twitter() {
	?>
  <input type="text" name="twitter" id="twitter" value="<?php
	
	echo get_option ( 'twitter' );
	?>" />
<?php
}
// Github
function setting_github() {
	?>
  <input type="text" name="github" id="github" value="<?php
	
	echo get_option ( 'github' );
	?>" />
<?php
}
```

## 3 - Save form data
```php
function custom_settings_page_setup() {
	add_settings_section ( 'section', 'All Settings', null, 'theme-options' );
	
	add_settings_field ( 'twitter', 'Twitter URL', array($this, 'setting_twitter'), 'theme-options', 'section' );
	add_settings_field ( 'github', 'GitHub URL', array($this, 'setting_github'), 'theme-options', 'section' );
	
	register_setting ( 'section', 'twitter' );
	register_setting ( 'section', 'github' );
}
```

## 4 - Register all functions in __construct()

```php

add_action ( 'admin_init', array($this, 'custom_settings_page_setup') );

```

## 5 - Use

```html
<li><a href="<?php echo get_option('github'); ?>">GitHub</a></li>
<li><a href="<?php echo get_option('twitter'); ?>">Twitter</a></li>
```