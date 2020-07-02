# Streams

* [stream_context_create - 创建资源流上下文](#streamcontextcreate)
* [stream_context_get_default - 检索默认资源流上下文](#streamcontextgetdefault)
* [stream_context_get_options - 获取资源流的参数](#streamcontextgetoptions)
* [stream_context_get_params - 从资源上下文中检索参数](#streamcontextgetparams)
* [stream_context_set_default - 设置默认资源流上下文](#streamcontextsetdefault)
* [stream_context_set_option - 对资源流设置参数](#streamcontextsetoption)
* [stream_context_set_params - 设置资源流的参数](#streamcontextsetparams)
* [stream_copy_to_stream - 将数据从一个资源流复制到另一个](#streamcopytostream)
* [stream_filter_append - 将过滤器附加到资源流](#streamfilterappend)
* [stream_filter_prepend - 将过滤器附加到资源流](#streamfilterprepend)
* [stream_filter_register - 注册用户自定义的资源流过滤器](#streamfilterregister)
* [stream_filter_remove - 从资源流里移除某个过滤器](#streamfilterremove)
* [stream_get_contents - 读取资源流到一个字符串](#streamgetcontents)
* [stream_get_filters - 获取已注册的数据流过滤器列表](#streamgetfilters)
* [stream_get_line - 从资源流里读取一行直到给定的定界符](#streamgetline)
* [stream_get_meta_data - 从封装协议文件指针中取得元数据](#streamgetmetadata)
* [stream_get_transports - 获取已注册的套接字传输协议列表](#streamgettransports)
* [stream_get_wrappers - 获取已注册的流类型](#streamgetwrappers)
* [stream_is_local - 检查流是否是本地流](#streamislocal)
* [stream_isatty - 检查流是否为 TTY](#streamisatty)
* [stream_register_wrapper - 注册一个用 PHP 类实现的 URL 封装协议](#streamregisterwrapper)
* [stream_resolve_include_path - 根据包含路径解析文件名](#streamresolveincludepath)
* [stream_set_blocking - 为资源流设置阻塞或者阻塞模式](#streamsetblocking)
* [stream_set_chunk_size - 设置资源流区块大小](#streamsetchunksize)
* [stream_set_read_buffer - 在给定的资源流上设置读取文件缓冲](#streamsetreadbuffer)
* [stream_set_timeout - 在资源流上设置超时时间](#streamsettimeout)
* [stream_set_write_buffer - 在给定的资源流上设置写文件缓冲](#streamsetwritebuffer)
* [stream_socket_accept - 接受套接字连接](#streamsocketaccept)
* [stream_socket_client - 打开 Internet 或 Unix 域套接字连接](#streamsocketclient)
* [stream_socket_enable_crypto - 在已连接的套接字上打开 / 关闭加密](#streamsocketenablecrypto)
* [stream_socket_get_name - 获取本地或者远程的套接字名称](#streamsocketgetname)
* [stream_socket_pair - 创建一对完全一样的网络套接字连接流](#streamsocketpair)
* [stream_socket_recvfrom - 从套接字接收数据，无论是否已连接](#streamsocketrecvfrom)
* [stream_socket_sendto - 将消息发送到套接字，无论是否已连接](#streamsocketsendto)
* [stream_socket_server - 创建一个 Internet 或 Unix 域服务器套接字](#streamsocketserver)
* [stream_socket_shutdown - 关闭全双工连接](#streamsocketshutdown)
* [stream_supports_lock - 告诉资源流是否支持锁定](#streamsupportslock)
* [stream_wrapper_register - 注册一个用 PHP 类实现的 URL 封装协议](#streamwrapperregister)
* [stream_wrapper_restore - 恢复之前的封装协议](#streamwrapperrestore)
* [stream_wrapper_unregister - 取消注册 URL 封装协议](#streamwrapperunregister)

## stream_context_create

```php
<?php

var_dump(stream_context_create());                                                                 // resource(4) of type (stream-context)
var_dump(stream_context_create(['http' => ['method' => 'GET', 'header' => 'Accept: text/html']])); // resource(5) of type (stream-context)

```

## stream_context_get_default

```php
<?php

var_dump(stream_context_get_default(['http' => ['method' => 'GET', 'header' => 'Accept: text/html']])); // resource(4) of type (stream-context)

```

## stream_context_get_options

```php
<?php

var_dump(stream_context_get_options(stream_context_get_default(['http' => ['method' => 'GET', 'header' => 'Accept: text/html']]))); // array(1) { ["http"]=> array(2) { ["method"]=> string(3) "GET" ["header"]=> string(17) "Accept: text/html" } }

```

## stream_context_get_params

```php
<?php

var_dump(stream_context_get_params(stream_context_create(['http' => ['method' => 'GET', 'header' => 'Accept: text/html']]))); // array(1) { ["options"]=> array(1) { ["http"]=> array(2) { ["method"]=> string(3) "GET" ["header"]=> string(17) "Accept: text/html" } } }

```

## stream_context_set_default

```php
<?php

var_dump(stream_context_set_default(['http' => ['method' => 'GET', 'header' => 'Accept: text/html']])); // resource(4) of type (stream-context)

```

## stream_context_set_option

```php
<?php

var_dump(stream_context_set_option(stream_context_create(), ['http' => ['method' => 'GET', 'header' => 'Accept: text/html']])); // bool(true)

```

## stream_context_set_params

```php
<?php

var_dump(stream_context_set_params(stream_context_create(), ['http' => ['method' => 'GET', 'header' => 'Accept: text/html']])); // bool(true)

```

## stream_copy_to_stream

```php
<?php

var_dump(stream_copy_to_stream(fopen('http://www.example.com', 'r'), fopen(__DIR__ . '/example.txt', 'w+')));

```

## stream_filter_append

```php
<?php

$handle = fopen(__DIR__ . '/example.txt', 'w+');
var_dump(stream_filter_append($handle, 'string.rot13', STREAM_FILTER_WRITE)); // resource(6) of type (stream filter)
fwrite($handle, 'foo');
rewind($handle);
var_dump(fgets($handle));                                                     // string(3) "sbb"

```

## stream_filter_prepend

```php
<?php

$handle = fopen(__DIR__ . '/example.txt', 'w+');
var_dump(stream_filter_prepend($handle, 'string.rot13', STREAM_FILTER_WRITE)); // resource(6) of type (stream filter)
fwrite($handle, 'foo');
rewind($handle);
var_dump(fgets($handle));                                                     // string(3) "sbb"

```

## stream_filter_register

```php
<?php

class Foo
{
    //
}

var_dump(stream_filter_register('foo', 'Foo')); // bool(true)

```

## stream_filter_remove

```php
<?php

$handle = fopen(__DIR__ . '/example.txt', 'w+');
$filter = stream_filter_append($handle, 'string.rot13', STREAM_FILTER_WRITE);
fwrite($handle, 'foo');
stream_filter_remove($filter);
fwrite($handle, 'foo');
rewind($handle);
var_dump(fgets($handle)); // string(6) "sbbfoo"

```

## stream_get_contents

```php
<?php

var_dump(stream_get_contents(fopen('http://www.example.com', 'r')));
var_dump(stream_get_contents(fopen('http://www.example.com', 'r'), 10));

```

## stream_get_filters

```php
<?php

var_dump(stream_get_filters());

```

## stream_get_line

```php
<?php

var_dump(stream_get_line(fopen('http://www.example.com', 'r'), 10));
var_dump(stream_get_line(fopen('http://www.example.com', 'r'), 10, '!'));

```

## stream_get_meta_data

```php
<?php

var_dump(stream_get_meta_data(fopen('http://www.example.com', 'r')));

```

## stream_get_transports

```php
<?php

var_dump(stream_get_transports());

```

## stream_get_wrappers

```php
<?php

var_dump(stream_get_wrappers());

```

## stream_is_local

```php
<?php

var_dump(stream_is_local(__FILE__));                             // bool(true)
var_dump(stream_is_local('http://www.example.com'));             // bool(false)
var_dump(stream_is_local(fopen('http://www.example.com', 'r'))); // bool(false)

```

## stream_isatty

```php
<?php

var_dump(stream_isatty(fopen(__FILE__, 'r')));

```

## stream_register_wrapper

```php
<?php

class Foo
{
    //
}

var_dump(stream_register_wrapper('foo', 'Foo')); // bool(true)

```

## stream_resolve_include_path

```php
<?php

var_dump(stream_resolve_include_path('index.php'));

```

## stream_set_blocking

```php
<?php

$handle = fopen('http://www.example.com', 'r');
var_dump(stream_set_blocking($handle, 0)); // bool(true)
var_dump(stream_set_blocking($handle, 1)); // bool(true)

```

## stream_set_chunk_size

```php
<?php

var_dump(stream_set_chunk_size(fopen('http://www.example.com', 'r'), 1024));

```

## stream_set_read_buffer

```php
<?php

var_dump(stream_set_read_buffer(fopen('http://www.example.com', 'r'), 1024)); // int(0)

```

## stream_set_timeout

```php
<?php

var_dump(stream_set_timeout(fopen('http://www.example.com', 'r'), 30)); // bool(true)

```

## stream_set_write_buffer

```php
<?php

var_dump(stream_set_write_buffer(fopen(__DIR__ . '/example.txt', 'w+'), 1024));

```

## stream_socket_accept

```php
<?php

var_dump(stream_socket_accept(stream_socket_server('tcp://127.0.0.1:80', $errno, $errstr), 2));

```

## stream_socket_client

```php
<?php

var_dump(stream_socket_client('tcp://127.0.0.1:80')); // resource(5) of type (stream)

```

## stream_socket_enable_crypto

```php
<?php

var_dump(stream_socket_enable_crypto(stream_socket_client('tcp://127.0.0.1:80'), false));

```

## stream_socket_get_name

```php
<?php

var_dump(stream_socket_get_name(stream_socket_client('tcp://www.example.com:80'), true));
var_dump(stream_socket_get_name(stream_socket_client('tcp://www.example.com:80'), false));

```

## stream_socket_pair

```php
<?php

var_dump(stream_socket_pair(STREAM_PF_UNIX, STREAM_SOCK_STREAM, STREAM_IPPROTO_IP));

```

## stream_socket_recvfrom

```php
<?php

$server = stream_socket_server('tcp://127.0.0.1:80');
$socket = stream_socket_accept($server, 2);
var_dump(stream_socket_recvfrom($socket, 1024));

```

## stream_socket_sendto

```php
<?php

$socket = stream_socket_client('tcp://127.0.0.1:80');
var_dump(stream_socket_sendto($socket, 'foo', STREAM_OOB)); // int(3)

```

## stream_socket_server

```php
<?php

var_dump(stream_socket_server('tcp://127.0.0.1:80', $errno, $errstr)); // resource(5) of type (stream)

```

## stream_socket_shutdown

```php
<?php

var_dump(stream_socket_shutdown(stream_socket_client('tcp://127.0.0.1:80'), STREAM_SHUT_WR)); // bool(true)

```

## stream_supports_lock

```php
<?php

var_dump(stream_supports_lock(stream_socket_client('tcp://127.0.0.1:80')));

```

## stream_wrapper_register

```php
<?php

class Foo
{
    //
}

var_dump(stream_wrapper_register('foo', 'Foo')); // bool(true)

```

## stream_wrapper_restore

```php
<?php

stream_wrapper_unregister('http');
var_dump(stream_wrapper_restore('http')); // bool(true)

```

## stream_wrapper_unregister

```php
<?php

class Foo
{
    //
}

stream_wrapper_register('foo', 'Foo');
var_dump(stream_wrapper_unregister('foo')); // bool(true)

```