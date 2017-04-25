## Custom router

```bash
function url () {

	$request = null;
	if (isset($_GET['PATH_INFO'])) {
		$request = explode('/', $_GET['PATH_INFO']);
		
	}
	else {

		$request = null;

	}

	return $request;

}






switch (true) {
    case url() == null:
        echo "home";
        break;
    case in_array("contact", url()) && count(url()) == 1:
        echo "contact";
        break;
    case in_array("contact", url()) /*&& in_array("me", url())*/ :
    	$data = url();
        echo $data[1];
        break;
    default:
       //echo "404";
    header("Location: /contact");
}


```