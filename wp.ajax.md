# Ajax login


```javascript

jQuery(document).ready(function ($) {
    
    // Envoie des données en ajax
    $('#form').on('submit', function (e) {
        e.preventDefault();
        $('.succès').show();
        var formData = new FormData(jQuery(this)[0]);

        jQuery.ajax({
            url: object.ajaxurl + '?action=ajax_process',
            type: 'POST',
            data: formData,
            success: function (data) {
               // alert(data);
                $('.succes').text("bravo" + data);
            },
            cache: false,
            contentType: false,
            processData: false
        });

        return false;
    });
});

```