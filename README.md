Deprecated
==========

You should rather use the [Dashboard Project](https://github.com/dbu/dashboard)
as this repository is abandoned. All functionality from this repository has been
ported into the dashboard project.

Github Data Client
==================

Rapidly losing the overview over the gazillion of pull requests on the many
bundles in various organizations that i maintain, I set out to build this tool
to see an overview of open pull requests.

This is still at a very early stage, but for me already a minimal viable
product.

[![Screenshot](doc/images/dashboard_screenshot_tn.png?raw=true)](doc/images/dashboard_screenshot.png?raw=true)


Installation
============

    curl -s http://getcomposer.org/installer | php
    ./composer.phar create-project dbu/github-cli github-cli

You will be prompted for your github credentials that will be stored plain text
in app/config/parameters.yml as well as the repositories configuration.
Configuring the repositories might be easier doing by editing the parameters.yml
file though.

(Reading would work without them, but you would be limited to 5000 requests per
hour.)


Usage
=====

Call `github:fetch` and pass organisation names or repositories as arguments:

    app/console github:fetch phpcr jackalope/jackalope-jackrabbit

You can also configure a default set of repositories to fetch in parameters.yml
This will be used if no repository is specified.


Ideas
=====

* Also count open issues that are no pull requests.
* Filter to only see new things or only very old (and make definition of "old" configurable).
  Show the "most important" issues?
* Gather information about git and show last tag and number of commits since that tag.
* ...


License
=======

This code is (c) 2013 by David Buchmann and may be used under the GNU Public License GPL.


Credits
=======

Most of the actual work of this tool is done by
[php-github-api](https://github.com/KnpLabs/php-github-api/) from the guys at KnpLabs.
