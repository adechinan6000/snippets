<?php


// AJAX
$(document).ready(function() {
    $('#monForm').on('submit', function(e) {
        e.preventDefault(); 
        var $this = $(this);
        var pseudo = $('#pseudo').val();
        var mail = $('#mail').val();
 
        if(pseudo === '' || mail === '') {
            alert('Les champs doivent êtres remplis');
        } else {
            $.ajax({
                url: $this.attr('action'),
                type: $this.attr('method'),
                data: $this.serialize(),
                dataType: 'json', // JSON
                success: function(json) {
                    if(json.reponse === 'ok') {
                        alert('Tout est bon');
                    } else {
                        alert('Erreur : '+ json.reponse);
                    }
                }
            });
        }
    });
});


if(isset($_POST['pseudo']) && isset($_POST['mail'])) {
    if(($_POST['pseudo'] !== '') && ($_POST['mail'] !== '')) {
        $reponse = 'ok';
    } else {
        $reponse = 'Les champs sont vides';
    }
} else {
    $reponse = 'Tous les champs ne sont pas parvenus';
}
 
echo json_encode(['reponse' => $reponse]);

-------------------------------------------------------------------------------------------------------------------------


// AJAX / AUTRE VARIATION

<script type="text/javascript">

        // Ajax post
        $(document).ready(function() {
            $(".submit").click(function(event) {
                event.preventDefault();
                var user_name = $("input#name").val();
                var password = $("input#pwd").val();
                jQuery.ajax({
                    type: "POST",
                    url: "<?php echo base_url("ajaxpost/user_data_submit");?>",
                    dataType: 'json',
                    data: {name: user_name, pwd: password},
                    success: function(res) {
                        if (res)
                        {
// Show Entered Value
                            jQuery("div#result").show();
                            jQuery("div#value").html(res.username);
                            jQuery("div#value_pwd").html(res.pwd);
                        }
                    }
                });
            });
        });
    </script>


    public function user_data_submit() {
        $data = array(
            'username' => $this->input->post('name'),
            'pwd'=>$this->input->post('pwd')
        );

//Either you can print value or you can send value to database
        echo json_encode($data);
    }

