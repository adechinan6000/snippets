## Custom package

```bash
http://blog.jgrossi.com/2013/creating-your-first-composer-packagist-package/

http://www.darwinbiler.com/creating-composer-package-library/
```

## Tuto

### Creating the Package

You can create a new project or update one to use Composer. I'll create a hello world class. It's a simple class but you can create complex projects and share them with the others developers. I'll use "hello-world" as project's name. Composer work in "vendor/package" name format. Here we can set as "vendor" name my name: "juniorgrossi" and as package name "hello-world", the name of the project.

### Files Structure

You can put all files inside the main dir, but I strongly recommend to create another dir, as "src" to be easier to understand and maintain your code organized. The project structure will start with the follow: * hello-world (root dir) * src * HelloWorld * SayHello.php Our SayHello.php file will have:

```bash
<?php 

namespace HelloWorld;

class SayHello
{
    public static function world()
    {
        return 'Hello World, Composer!';
    }
}
```

### Starting Composer

```bash
{
    "name": "juniorgrossi/hello-world",
    "description": "My first Composer project",
    "authors": [
        {
            "name": "Your Name",
            "email": "your@name.com"
        }
    ],
    "minimum-stability": "dev",
    "require": {

    }
}

Do you confirm generation [yes]? yes
 Now you have "composer.json" file saved in your root dir. It's almost ready but we must do some changes: 

{
    "name": "juniorgrossi/hello-world",
    "description": "My first Composer project",
    "authors": [
        {
            "name": "Your Name",
            "email": "your@name.com"
        }
    ],
    "minimum-stability": "dev",
    "require": {
        "php": ">=5.3.0"
    },
    "autoload": {
        "psr-4": {
            "Eutrinos\\":"controllers/"
        }
    }
}
```

Load all controllers inside controllers folder starting by Eutrinos namespace: 

Exemple:
```bash
controllers/Hello.php
namespace Eutrinos;

class Hello {


	function hi() {
		$request = explode('/', $_GET['PATH_INFO']);
		require_once 'views/hi.php';
	}

}

index.php
use Eutrinos\Hello;
$hello = new Hello();
$hello->hi();
```

### Testing Package

```bash
composer install
```

```bash
require_once __DIR__ . '/../vendor/autoload.php'; // Autoload files using Composer autoload

use HelloWorld\SayHello;

echo SayHello::world();
 Go to the terminal (or create a PHP web server inside "tests" dir) and type: 

php tests/test.php
```

### Sending to Packagist.org

Now your project is working and you want to send it to Packagist. The easy way is push your project to Github using Git. Go to Github and create a new public repo called "helloworld", start the Git project inside your root dir and push it:

```bash
git init 
git add . 
git commit -m "First commit" 
git remote add origin git@github.com:username/helloworld.git 
git push origin master
```
Now you have your project inside a Github repo and you're ready to send it to Packagist. Go to Packagist web site, create your account, login and Submit a Package. Packagist'll ask you for Repository URL (Git/Svn/Hg). Paste there git@github.com:username/helloworld.git and click "Check!". Packagist will check your project and return the project name. If it's correct accept it.

### Packagist Details

```bash
Every time you do a new commit to Github you must update the Packagist. Go to your account, your package and click "Force Update!". Packagist will go to Github and update the sources. You can turn on "auto update" going to your Github repo, clicking "Settings", after "Service Hooks" and click the "Packagist" service. There update with your information, like:

    User: your Packagist username, like juniorgrossi
    Token: your API token, that you can find inside your Packagist settings link
    Domain: packagist.org Ok! Auto update finished and your package is available to other developers.

Our first Composer package is finished, but you can do much more using it. Thanks!
```