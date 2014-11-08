drupal-behat
============

This repository is the source of `cashwilliams/drupal-behat` which brings :  
- php5-cli with PHP 5.5  
- drupal-extension
- drush
- all needed dependencies  

## Install

    docker pull cashwilliams/drupal-behat

## Usage

On your host, you can add the `behat()` function to your shell environnement:  

    function behat() { docker run -t -i --rm -h drupal-behat -v $(pwd):/home/behat/data:rw cashwilliams/drupal-behat /bin/bash -c "behat $*" ;}

You can now call `behat` command from your host, it will be executed in your docker container.
Note that the container will be removed when the behat process will end usins `--rm`.  
A `data` folder is mounted read/write to your current folder (the one you launched docker-behat).  

Or:

    docker run -t -i -h drupal-behat -v $(pwd):/home/behat/data:rw cashwilliams/drupal-behat /bin/bash

You should see a prompt with the `behat` command available.  

## Build

If you need adapt the project to your needs, clone, modify the `Dockerfile` and from the source directory, run:

    docker build -t cashwilliams/drupal-behat .

Also available via [Docker Index](https://index.docker.io/u/cashwilliams/drupal-behat/).
