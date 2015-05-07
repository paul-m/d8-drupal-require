Adding A Dependency To Drupal 8 Using Composer
===

Status
---
[![Build Status](https://travis-ci.org/paul-m/d8-drupal-require.svg?branch=master)](https://travis-ci.org/paul-m/d8-drupal-require)

What?
---

This repo is a test of whether you can use Composer to add a dependency to an existing Drupal codebase.

It uses github and travis-ci to build a Drupal installation and then try to run tests.

We are limiting the tests to PHPUnit, because that will give us a good indication of whether autoloading is working properly.

We are performing this sequence of commands in travis-ci:

    $ composer require crell/api-problem
    $ ./vendor/bin/phpunit -c core/

How?
---

The travis-ci build happens whenever someone pushes to this repo. If you don't have access, you can't push against this repo (and you don't). You can, however, choose from the following options:

* Fork your own repo, and push to your own repo to your heart's content.
* Perform the test locally. Just clone the Drupal 8 repo and perform the commands listed in the What? section.

Why?
---

Drupal 8's current double-front-controller-to-the-autoloader strategy doesn't make any sense.

We can fix it in this issue: https://www.drupal.org/node/2380389
