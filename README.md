Use composer dependency management with OXID
=======

Introduction
------------
Composer is a tool for dependency management in PHP. It allows you to declare the dependent libraries your project needs and it will install them in your project for you.
This guide will help you, to build manage your custom modules and themes via composer and install them to OXID.

Installation
------------
Installation instructions for composer can be found [here][1]

 1. Copy the example composer.json file to your project
 2. Open your modules/functions.php file
 3. Put the following line at the end of the file:
```require __DIR__ . '/../vendor/autoload.php';```
 4. Run ```composer install``` from CLI
 5. Installation is complete.

Managing custom modules via composer
------------

1. Fork the repository at https://github.com/superReal/composer-with-oxid-demo-module
2. Modify it to your needs
3. Adapt the composer.json file
4. Define a dependency in your projects root composer.json file. For using private repositores refer to https://getcomposer.org/doc/05-repositories.md#using-private-repositories
5. Run ```composer update``` to install the module
6. Activate it in the OXID backend

Managing custom themes via composer
------------

1. Fork the repository at https://github.com/superReal/composer-with-oxid-demo-theme
2. Modify it to your needs
3. Adapt the composer.json file
4. Define a dependency in your projects root composer.json file. For using private repositores refer to https://getcomposer.org/doc/05-repositories.md#using-private-repositories
5. Add the post-autoload-dump-scripts, to symlink the assets to the out/ folder automatically, after installing

  ```
  "scripts": {
        "post-autoload-dump": [
            "ln -sf ../application/views/composer-with-oxid-demo-theme/skin/composer-with-oxid-demo-theme out/composer-with-oxid-demo-theme"
        ]
    }
  ```
6. Run ```composer update``` to install the theme
7. Activate it in the OXID backend

Contributing
------------

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

[1]: https://getcomposer.org/doc/00-intro.md#installation-nix