# Readme

- clone this: git@github.com:adechinan6000/sb-simple.git
- folder structure:

* src
    * main
        * java
            * com.package
                * controllers
                * domains
                * repositories
                * services
                * Application.java
        * resources
            * messages
                * messages_en.properties
            * static
                * css
                * js
            * templates
                * home.html
            * application.properties
* uploads

- don't use controllers, and services if you use  spring-data-rest 
which already contains built in controllers

- if you plan to add new controllers and services you can then use them

- step
    * internationalisation
    * domains
    * repositories
    * services
    * controllers
    * views
    * uploads
    * security - session
