# URL

* [base64_decode - 对使用 MIME base64 编码的数据进行解码](#base64decode)
* [base64_encode - 使用 MIME base64 对数据进行编码](#base64encode)
* [get_headers - 取得服务器响应一个 HTTP 请求所发送的所有报头](#getheaders)
* [get_meta_tags - 从一个文件中提取所有的 meta 标签 content 属性，返回一个数组](#getmetatags)
* [http_build_query - 生成 URL-encode 之后的请求字符串](#httpbuildquery)
* [parse_url - 解析 URL ，返回其组成部分](#parseurl)
* [rawurldecode - 对已编码的 URL 字符串进行解码](#rawurldecode)
* [rawurlencode - 按照 RFC 3986 对 URL 进行编码](#rawurlencode)
* [urldecode - 对已编码的 URL 字符串进行解码](#urldecode)
* [urlencode - 编码 URL 字符串](#urlencode)

## base64_decode

```php
<?php

var_dump(base64_decode('Zm9v'));    // string(3) "foo"
var_dump(base64_decode('_'));       // string(0) ""
var_dump(base64_decode('_', true)); // bool(false)

```

## base64_encode

```php
<?php

var_dump(base64_encode('foo')); // string(4) "Zm9v"
var_dump(base64_encode('_'));   // string(4) "Xw=="
var_dump(base64_encode(' '));   // string(4) "IA=="

```

## get_headers

```php
<?php

var_dump(get_headers('https://github.com/'));
var_dump(get_headers('https://github.com/', 1));

```

## get_meta_tags

```php
<?php

var_dump(get_meta_tags('https://github.com/'));
var_dump(get_meta_tags(__DIR__ . '/example.html', true));

```

上例中的 `example.html` 文件内容：

```html
<!DOCTYPE html>
<html lang="zh-cmn-Hans">
    <head>
        <meta charset="utf-8"/>
        <meta name="foo" content="foo"/>
        <meta name="bar" content="bar"/>
    </head>
    <body>
    </body>
</html>
```

## http_build_query

```php
<?php

var_dump(http_build_query(['foo' => 'cat', 'bar' => 'dog']));                            // string(15) "foo=cat&bar=dog"
var_dump(http_build_query(['foo' => 'cat', 'bar' => ['dog']]));                          // string(22) "foo=cat&bar%5B0%5D=dog"
var_dump(http_build_query(['foo', 'bar'], 'prefix_'));                                   // string(25) "prefix_0=foo&prefix_1=bar"
var_dump(http_build_query(['foo', 'bar'], 'prefix_', '&amp;'));                          // string(29) "prefix_0=foo&amp;prefix_1=bar"
var_dump(http_build_query(['foo' => 'cat dog'], 'prefix_', '&amp;', PHP_QUERY_RFC1738)); // string(11) "foo=cat+dog"
var_dump(http_build_query(['foo' => 'cat dog'], 'prefix_', '&amp;', PHP_QUERY_RFC3986)); // string(13) "foo=cat%20dog"

```

## parse_url

```php
<?php

var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor'));                   // array(8) { ["scheme"]=> string(4) "http" ["host"]=> string(8) "hostname" ["port"]=> int(80) ["user"]=> string(8) "username" ["pass"]=> string(8) "password" ["path"]=> string(5) "/path" ["query"]=> string(9) "arg=value" ["fragment"]=> string(6) "anchor" }
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_SCHEME));   // string(4) "http"
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_HOST));     // string(8) "hostname"
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_PORT));     // int(80)
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_USER));     // string(8) "username"
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_PASS));     // string(8) "password"
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_PATH));     // string(5) "/path"
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_QUERY));    // string(9) "arg=value"
var_dump(parse_url('http://username:password@hostname:80/path?arg=value#anchor', PHP_URL_FRAGMENT)); // string(6) "anchor"

```

## rawurldecode

```php
<?php

var_dump(rawurldecode('foo%3Dcat%26bar%3Ddog'));       // string(15) "foo=cat&bar=dog"
var_dump(rawurldecode('foo%3Dcat%26bar%3D%20dog%20')); // string(17) "foo=cat&bar= dog "
var_dump(rawurldecode('foo%3Dcat%26bar%3Ddog+bird'));  // string(20) "foo=cat&bar=dog+bird"

```

## rawurlencode

```php
<?php

var_dump(rawurlencode('foo=cat&bar=dog'));      // string(21) "foo%3Dcat%26bar%3Ddog"
var_dump(rawurlencode('foo=cat&bar= dog '));    // string(27) "foo%3Dcat%26bar%3D%20dog%20"
var_dump(rawurlencode('foo=cat&bar=dog bird')); // string(28) "foo%3Dcat%26bar%3Ddog%20bird"

```

## urldecode

```php
<?php

var_dump(urldecode('foo%3Dcat%26bar%3Ddog'));       // string(15) "foo=cat&bar=dog"
var_dump(urldecode('foo%3Dcat%26bar%3D%20dog%20')); // string(17) "foo=cat&bar= dog "
var_dump(urldecode('foo%3Dcat%26bar%3Ddog+bird'));  // string(20) "foo=cat&bar=dog bird"

```

## urlencode

```php
<?php

var_dump(urlencode('foo=cat&bar=dog'));      // string(21) "foo%3Dcat%26bar%3Ddog"
var_dump(urlencode('foo=cat&bar= dog '));    // string(23) "foo%3Dcat%26bar%3D+dog+"
var_dump(urlencode('foo=cat&bar=dog bird')); // string(26) "foo%3Dcat%26bar%3Ddog+bird"

```