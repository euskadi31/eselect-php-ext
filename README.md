Gentoo eselect PHP Extentions module
====================================

Activate and Deactivate php extensions on Gentoo.

Install
-------

Copy the `php-ext.eselect` file in the folder `/usr/share/eselect/modules/`

Usage
-----

~~~shell
localhost ~ # eselect php-ext
Usage: eselect php-ext <action> <options>

Standard actions:
  help                      Display help text
  usage                     Display usage information
  version                   Display version information

Extra actions:
  list <module>             Lists available php extensions installs for a module
    module                    one of cli apache2 fpm cgi
  set <module> <target>     Sets a php extensions for a module
    module                    one of cli apache2 fpm cgi
    target                    Target name or number (from the 'list' action)
  unset <module> <target>   Unsets a php extensions for a module
    module                    one of cli apache2 fpm cgi
    target                    Target name or number (from the 'list' action)
~~~

List PHP extensions for cli module
~~~
localhost ~ # eselect php-ext list cli
  [1]   geoip *
  [2]   http *
  [3]   xdebug
~~~

List PHP extensions for fpm module
~~~
localhost ~ # eselect php-ext list fpm
  [1]   geoip *
  [2]   http *
  [3]   xdebug *
~~~

Activate xdebug extension on current PHP
~~~shell
eselect php-ext set cli xdebug
~~~

Deactivate http extension on current PHP
~~~shell
eselect php-ext set cli http
~~~