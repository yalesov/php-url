# Yalesov\Url

[![Build Status](https://secure.travis-ci.org/yalesov/url.png)](http://travis-ci.org/yalesov/url)

A collection of url-related functions.

# Installation

[Composer](http://getcomposer.org/):

```json
{
    "require": {
        "yalesov/url": "1.*"
    }
}
```

# Usage

Turn a URL, relative or absolute, into an absolute URL:

```php
use Yalesov\Url\Url;
$url = Url::toAbsolute($baseUrl, $relativeUrl);
```

Filter out `.` and `..` segments from URL's path:

```php
use Yalesov\Url\Url;
$path = Url::removeDotSegments($path);
```

Split a URL to its components: (reverse of `Url::join()`)

```php
use Yalesov\Url\Url;
$parts = Url::split($url);
// one or more of the following keys may be present:
// $parts['scheme']     = (scheme, such as "http")
// $parts['host']       = (host name, IPv4, or IPv6 address)
// $parts['port']       = (the port number)
// $parts['user']       = (user name)
// $parts['pass']       = (user password)
// $parts['path']       = (path, e.g. a file path for "http")
// $parts['query']      = (the query)
// $parts['fragment']   = (the fragment)
```

Join together URL components to form a complete URL: (reverse of `Url::split()`)

```php
use Yalesov\Url\Url;
$url = Url::join(array(
    'scheme'    => $scheme,
    'host'      => $host,
    'port'      => $port,
    'user'      => $user,
    'pass'      => $pass,
    'path'      => $path,
    'query'     => $query,
    'fragment'  => $fragment,
));
```
