# Create Section

```php
add_filter( 'woocommerce_get_sections_products', 'wcslider_add_section' );
function wcslider_add_section( $sections ) {
	
	$sections['wcslider'] = __( 'WC Slider', 'text-domain' );
	return $sections;
	
}
```