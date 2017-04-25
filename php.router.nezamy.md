## Dependencies

```bash
composer require nezamy/route
```


## Tuto 1

```bash
require_once 'vendor/autoload.php';

define('DS', DIRECTORY_SEPARATOR, true);
define('BASE_PATH', __DIR__ . DS, TRUE);

$app            = System\App::instance();
$app->request   = System\Request::instance();
$app->route     = System\Route::instance($app->request);

$route          = $app->route;

$route->any('/', function() {
    echo 'Hello World';
});

$route->end();
```

## Tuto 2

```bash
/////

$route          = $app->route;

class home
{
    function pages() {
        echo 'Home page Content';
    }
}
$route->get('/', [$home, 'pages']);
// OR
$route->get('/', 'home@pages');

$route->end();
```

## Method routing

```bash
$route->any('/', function() {
    // Any method requests
});

$route->get('/', function() {
    // Only GET requests
});

$route->post('/', function() {
    // Only POST requests
});

$route->put('/', function() {
    // Only PUT requests
});

$route->patch('/', function() {
    // Only PATCH requests
});

$route->delete('/', function() {
    // Only DELETE requests
});

// You can use multiple methods. Just add _ between method names
$route->get_post('/', function() {
    // Only GET and POST requests
});
```

## Multiple Routing (All in one)

```bash
$route->get(['/', 'index', 'home'], function() {
    // Will match 3 page in one
});
```

## Parameters

```bash
// This example will match any page name
$route->get('/?', function($page) {
    echo "you are in $page";
});

// This example will match anything after post/ - limited to 1 argument
$route->get('/post/?', function($id) {
    // Will match anything like post/hello or post/5 ...
    // But not match /post/5/title
    echo "post id $id";
});

// more than parameters
$route->get('/post/?/?', function($id, $title) {
    echo "post id $id and title $title";
});
```

## Named Parameters

```bash
$route->get('/{username}/{page}', function($username, $page) {
    echo "Username $username and Page $page <br>";
    // OR
    echo "Username {$this['username']} and Page {$this['page']}";
});
```

## Optional param

```bash
$route->get('/post/{title}?:title/{date}?',
function($title, $date) {
    if ($title) {
        echo "<h1>$title</h1>";
    }else{
        echo "<h1>Posts List</h1>";
    }

    if ($date) {
        echo "<small>Published $date</small>";
    }
});
```

## Groups

```bash
$route->group('/admin', function()
{
    // /admin/
    $this->get('/', function() {
        echo 'welcome to admin panel';
    });

    // /admin/settings
    $this->get('/settings', function() {
        echo 'list of settings';
    });

    // nested group
    $this->group('/users', function()
    {
        // /admin/users
        $this->get('/', function() {
            echo 'list of users';
        });

        // /admin/users/add
        $this->get('/add', function() {
            echo 'add new user';
        });
    });

    // Anything else
    $this->any('/*', function() {
        pre("Page ( {$this->app->request->path} ) Not Found", 6);
    });
});
```

## Groups with params

```bash
$route->group('/{lang}?:isoCode2', function($lang)
{
    $default = $lang;

    if (!in_array($lang, ['ar', 'en'])) {
        $default = 'en';
    }

    $this->get('/', function($lang) use($default) {
        echo "lang in request is $lang<br>";
        echo "include page_{$default}.php";
    });

    $this->get('/page/{name}/', function($lang, $name)
    {
        pre(func_get_args());
        pre($this->app->request->args);
    });
});
```