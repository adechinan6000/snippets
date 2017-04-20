# Sending mail

## Config

```bash
# app/config/config.yml
swiftmailer:
    transport: '%mailer_transport%'
    host:      '%mailer_host%'
    username:  '%mailer_user%'
    password:  '%mailer_password%'
```

## Sending mail

```php
public function indexAction($name)
{
    $message = \Swift_Message::newInstance()
        ->setSubject('Hello Email')
        ->setFrom('send@example.com')
        ->setTo('recipient@example.com')
        ->setBody(
            $this->renderView(
                // app/Resources/views/Emails/registration.html.twig
                'Emails/registration.html.twig',
                array('name' => $name)
            ),
            'text/html'
        )
        /*
         * If you also want to include a plaintext version of the message
        ->addPart(
            $this->renderView(
                'Emails/registration.txt.twig',
                array('name' => $name)
            ),
            'text/plain'
        )
        */
    ;
    $this->get('mailer')->send($message);

    return $this->render(...);
}
```

## Rendering

```php
{# app/Resources/views/Emails/registration.html.twig #}
<h3>You did it! You registered!</h3>

Hi {{ name }}! You're successfully registered.

{# example, assuming you have a route named "login" #}
To login, go to: <a href="{{ url('login') }}">...</a>.

Thanks!

{# Makes an absolute URL to the /images/logo.png file #}
<img src="{{ absolute_url(asset('images/logo.png')) }}">
```