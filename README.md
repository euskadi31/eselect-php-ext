Gentoo eselect PHP Extentions module
====================================

Activate and Deactivate php extensions on Gentoo.

Install
-------

Copy the `php-ext.eselect` file in the folder `/usr/share/eselect/modules/`

Usage
-----

Manage your php extensions by module (cli, fpm, cgi, apache2) and version (php 5.3, php 5.4 and php 5.5)

~~~shell
localhost ~ # eselect php-ext
Usage: eselect php-ext <action> <options>

Standard actions:
  help                      Display help text
  usage                     Display usage information
  version                   Display version information

Extra actions:
  list <module> <php-version>
                            Lists available php extensions installs for a module
    module                    one of cli apache2 fpm cgi
    php-version               PHP version (5.5, 5.4, 5.3) By default uses the activated php version
  set <module> <target> <php-version>
                            Sets a php extensions for a module
    module                    one of cli apache2 fpm cgi
    target                    Target name or number (from the 'list' action)
    php-version               PHP version (5.5, 5.4, 5.3) By default uses the activated php version
  unset <module> <target> <php-version>
                            Unsets a php extensions for a module
    module                    one of cli apache2 fpm cgi
    target                    Target name or number (from the 'list' action)
    php-version               PHP version (5.5, 5.4, 5.3) By default uses the activated php version
~~~

Lists PHP extensions for cli module (php5.4 is activate by `eselect php`)
~~~
localhost ~ # eselect php-ext list cli
PHP Version : php5.4
  [1]   geoip *
  [2]   http *
  [3]   xdebug
~~~

Lists PHP extensions for cli module and php 5.5 version
~~~
localhost ~ # eselect php-ext list cli 5.5
PHP Version : php5.5
  [1]   opcache *
~~~

Lists PHP extensions for fpm module
~~~
localhost ~ # eselect php-ext list fpm
PHP Version : php5.4
  [1]   geoip *
  [2]   http
  [3]   xdebug *
~~~

Activate xdebug extension on activate PHP
~~~shell
eselect php-ext set cli xdebug
~~~

Activate xdebug extension on PHP version
~~~shell
eselect php-ext set cli xdebug 5.4
~~~

Deactivate http extension on activate PHP
~~~shell
eselect php-ext set cli http
~~~

Deactivate http extension on PHP version
~~~shell
eselect php-ext set cli http 5.4
~~~