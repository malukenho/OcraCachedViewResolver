# OcraCachedViewResolver

OcraCachedViewResolver is performance-oriented Zend Framework 2 Module that increases performance
in your application by caching the process of resolving template names to paths.

In ZF2, the process of resolving template paths causes a lot of stat calls. This module adds
a cache layer to avoid that.

## Installation

The recommended way to install `ocramius/ocra-cached-view-resolver` is through
[composer](http://getcomposer.org/):

```sh
php composer.phar require ocramius/ocra-cached-view-resolver
```

When asked for a version to install, type `*`.
You can then enable the module in your `config/application.config.php`.

## Configuration

The only configurable setting for this module is how the cache adapter has to be generated.
By default, a `Zend\Cache\Storage\Adapter\Apc` is used. You can change this behavior by
defining following config in your application:

```php
return array(
    'ocra_cached_view_resolver' => array(
        'cache' => array(
            // configuration to be passed to `Zend\Cache\StorageFactory#factory()` here
        ),
    ),
);
```

## Testing

After having installed via composer:

```sh
cd path/to/ocra-cached-view-resolver
phpunit
```