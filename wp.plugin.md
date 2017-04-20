# Plugin starter

```php

/*
Plugin Name: Sample Plugin (With Ajax)
Description: Sample Plugin
Author: Stak
*/

define ('ASSET', plugins_url('pluginnamefolder/assets/'));

class FormAjax
{
    function __construct()
    {
        add_action( 'wp_enqueue_scripts', array($this, 'enqueueScript') );
        add_shortcode( 'form_ajax', array($this, 'form_ajax') );
        add_action( 'wp_ajax_ajax_process', array($this, 'ajax_process') );
        add_action( 'wp_ajax_nopriv_ajax_process',  array($this, 'ajax_process') );

    }

    function enqueueScript() {

        wp_enqueue_script( 'ajax', ASSET. 'js/ajax.js', array( 'jquery' ), false, true );
        wp_localize_script('ajax', 'object', ['ajaxurl' => admin_url('admin-ajax.php')]);
        wp_enqueue_style( 'slider', ASSET. '/css/slider.css',false,'1.1','all');
    }

    function form_ajax() {}

    function ajax_process() {}
}

$formAjax = new FormAjax();

```