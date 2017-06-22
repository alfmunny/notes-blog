---
title: Laravel Installation
date: 2017-06-21 13:23:21
tags: [lavarel]
toc: true
---
<!-- toc -->

## installation

Several packages should be installed.

* php 7.1
* composer
* lavarel
* valet
* mysql

### php7.1

    brew install homebrew/php/php71

### composer

copy following code into terminal and execute

    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php
    php -r "unlink('composer-setup.php');"


move the composer.phar into your PATH

    mv composer.phar /usr/local/bin/composer


add the composer vendor into your PATH

    export PATH="$HOME/.composer/vendor/bin:$PATH"

### lavarel

    composer global require lavarel/installer

### valet 

    composer global require lavarel/valet
    valet install

Than you can ping foo.dev
    ping foo.dev

### mysql

    brew install mysql
    brew service start mysql

## Create new project

    cd ~/code
    valet park
    laravel new anything

Than you can visit anything.dev in your browser.

Notes: if the website only shows you 'it works!', try followings:

    sudo apachectl stop
    valet restart

You can secure the website by

    cd anything
    valet secure

