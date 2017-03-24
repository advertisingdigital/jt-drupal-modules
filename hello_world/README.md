## Installation

* Follow the standard [Drupal module installation](https://drupal.org/documentation/install/modules-themes)
  process

#### Automatically With Drush (Recommended)

Using `drush en` and `drush dis` to enable and disable modules respectively will
automatically generate the consolidated `composer.json` file and run the
appropriate Composer commands to install and update the required dependencies.

#### Example

# $ drush en hello_world
# The following extensions will be enabled: hello_world
# Do you really want to continue? (y/n): y
# hello_world was enabled successfully.                                [ok]
# One or more extensions have dependencies managed by Composer.
# Update packages managed by Composer? (y/n): y
# Loading composer repositories with package information
# Updating dependencies (including require-dev)
#  - Installing symfony/polyfill-php54 (v1.3.0)
#    Loading from cache

#  - Installing symfony/http-foundation (v2.8.0)
#    Loading from cache

# Writing lock file
# Generating autoload files
# $

#### Manually With Composer

If you do not wish to use Drush, you must manually use Composer's command line
tool to install and update dependencies whenever modules are enabled or
disabled. The following steps illustrate the workflow to maintain the
dependencies required by contributed module:

* Visit `admin/modules` and enable / disable the modules that have dependencies
* Change into the the "Composer File Directory" as configured in Composer
  Manager's settings page which is where the consolidated `composer.json` file
  was generated
* If necessary, [download and install](https://github.com/composer/composer/blob/master/doc/01-basic-usage.md#installation)
  the Composer tool
* Run `php composer.phar install --no-dev` on the command line, replace
  `install` with `update` when updating dependencies

Refer to [Composer's documentaton](https://getcomposer.org/doc/) for more
details on how Composer works.