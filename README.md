# OroCRM Application

Welcome to OroCRM an Open Source Customer Relationship Management (CRM) tool.

**Important Note**: this application is not production ready and is intended for evaluation and development only.

## Requirements

OroCRM is Symfony 2 based application with following requirements:

* PHP 5.4.4 and above
* PHP Extensions
    * GD
    * Mcrypt
    * JSON
    * ctype
    * Tokenizer
    * SimpleXML
    * PCRE
    * ICU
* MySQL 5.1 and above

## Installation instructions

OroCRM uses [Composer][1] to manage package dependencies, this is the a recommended way to install OroCRM.

If you don't have Composer yet, download it following the instructions on http://getcomposer.org/
or just run the following command:

```bash
    curl -s https://getcomposer.org/installer | php
```

- Clone https://github.com/orocrm/crm-application.git OroCRM project with:

```bash
    git clone http://github.com/orocrm/crm-application.git
```

- Go to app/config folder and create parameters.yml using parameters.yml.dist as example. Update database name and credentials.
  Alternatively parameters.yml can be created automatically on the next step when run composer install command,
  you will be able to customize all the values interactively.

- Install OroCRM dependencies with composer. If installation process seems too slow you can use "--prefer-dist" option.

```bash
    php composer.phar install --prefer-dist
```

- Create the database (default name is "oro_crm").

- Initialize application with Installation Wizard by opening install.php in the browser or from CLI:

```bash  
app/console oro:install
```

- After installation you can login as application administrator using user name "admin" and password "admin".

Instant messaging between the browser and the web server
--------------------------------------------------------
To use this feature you need to configure parameters.yml websocket parameters and run server with console command

```bash
app/console clank:server --env prod
```

Reporting
---------
To use this feature you need to run report data collector with console command

```bash
app/console oro:report:update --env prod
```

Demo Data uploading
---------
To upload this feature you need to run console command

 ```bash
php app/console oro:installer:fixtures:load --env prod --fixtures-type=demo
```

Checking your System Configuration
-------------------------------------

Before starting to code, make sure that your local system is properly
configured for a Symfony application.

Execute the `check.php` script from the command line:

```bash
    php app/check.php
```

Access the `config.php` script from a browser:

    http://your_domain/path/to/symfony/app/web/config.php

If you get any warnings or recommendations, fix them before moving on.


[1]:  http://symfony.com/doc/2.3/book/installation.html
[2]:  http://getcomposer.org/
