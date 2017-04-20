# Create custom post type

```php

function create_cpt() {

		$my_post = array(
			'post_type'=> 'livre',
			'post_title'    => wp_strip_all_tags( $_POST['title'] ),
			'post_excerpt'  => sanitize_text_field($_POST['excerpt']),
			'post_status'   => 'pending',
			'post_author'   => get_current_user_id(),
			'meta_input' => array(
				'livre' => ['number' => sanitize_text_field($_POST['number']),
				            'text' => sanitize_text_field($_POST['author'])],
			),
			'post_category' =>  array($_POST['cat']),

		);

		// Insertion du livre en bd
		$parent_post_id = wp_insert_post( $my_post );


		// Inclusion d la librairie manipulant les fichiers
		if (!function_exists('wp_handle_upload')) {
			require_once ABSPATH . 'wp-admin/includes/file.php';
		}

		// Envoie de l'image de couverture au serveur
		$movefile = wp_handle_upload($_FILES['file'], ['test_form' => false]);

		// Si l'upload se passe bien :
		if ($movefile && !isset($movefile['error'])) {
			$filename = $movefile['file'];
			$filetype = wp_check_filetype(basename($filename), null);
			$wp_upload_dir = wp_upload_dir();

			$attachment = array(
				'guid' => $wp_upload_dir['url'] . '/' . basename($filename),
				'post_mime_type' => $filetype['type'],
				'post_title' => preg_replace('/\.[^.]+$/', '', basename($filename)),
				'post_content' => '',
				'post_status' => 'inherit',
			);

			// lié le fichier image au livre
			$attach_id = wp_insert_attachment( $attachment, $filename, $parent_post_id );

			// si la liaision se passe bien :
			if($attach_id) {
				require_once ABSPATH . 'wp-admin/includes/image.php';

				// Mettre à jour
				$attach_data = wp_generate_attachment_metadata($attach_id, $filename);
				wp_update_attachment_metadata($attach_id, $attach_data);

				set_post_thumbnail( $parent_post_id, $attach_id );
			}

			echo 'Success!';
		} else {
			echo $movefile['error'];
		}

		die();
	}



```