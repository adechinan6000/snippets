# Cpt read single


## make this code available in a custom template file

```php
$args =  array( 
				'post_type' => 'my-custom-post',
			  );
$custom_query = new WP_Query( $args );
$custom_query->the_post();
the_permalink();
the_title();
the_content();
the_post_thumbnail();

```


## add this in a function and register it in __construct()

```php
function form_page_template () {
       if (is_single() && is_post_type('film')){
           $page_template = dirname( __FILE__ ) . '/templates/mona.php';
           return $page_template;
       }
}
```

## register it in __construct()
```php
add_filter( 'page_template', array($this, 'form_page_template') );
```