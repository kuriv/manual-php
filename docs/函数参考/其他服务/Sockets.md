# Sockets



## socket_accept

```php

```

## socket_addrinfo_bind

```php

```

## socket_addrinfo_connect

```php

```

## socket_addrinfo_explain

```php

```

## socket_addrinfo_lookup

```php

```

## socket_bind

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_bind($socket, '127.0.0.2')); // bool(true)

```

## socket_clear_error

```php
<?php

socket_clear_error();
socket_clear_error(socket_create(AF_INET, SOCK_STREAM, SOL_TCP));

```

## socket_close

```php
<?php

var_dump(socket_close(socket_create(AF_INET, SOCK_STREAM, SOL_TCP)));

```

## socket_connect

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.2');
var_dump(socket_connect($socket, '127.0.0.1', 80)); // bool(true)

```

## socket_create_listen

```php

```

## socket_create_pair

```php

```

## socket_create

```php
<?php

var_dump(socket_create(AF_INET, SOCK_STREAM, SOL_TCP));  // resource(4) of type (Socket)
var_dump(socket_create(AF_INET6, SOCK_STREAM, SOL_TCP)); // resource(5) of type (Socket)
var_dump(socket_create(AF_UNIX, SOCK_STREAM, SOL_TCP));  // resource(6) of type (Socket)

```

## socket_export_stream

```php

```

## socket_get_option

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_get_option($socket, SOL_SOCKET, SO_DEBUG));
var_dump(socket_get_option($socket, SOL_SOCKET, SO_KEEPALIVE));
var_dump(socket_get_option($socket, SOL_SOCKET, SO_LINGER));

```

## socket_getopt

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_getopt($socket, SOL_SOCKET, SO_DEBUG));
var_dump(socket_getopt($socket, SOL_SOCKET, SO_KEEPALIVE));
var_dump(socket_getopt($socket, SOL_SOCKET, SO_LINGER));

```

## socket_getpeername

```php

```

## socket_getsockname

```php

```

## socket_import_stream

```php

```

## socket_last_error

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_last_error()); // int(0)

```

## socket_listen

```php

```

## socket_read

```php

```

## socket_recv

```php

```

## socket_recvfrom

```php

```

## socket_recvmsg

```php

```

## socket_select

```php

```

## socket_send

```php

```

## socket_sendmsg

```php

```

## socket_sendto

```php

```

## socket_set_block

```php

```

## socket_set_nonblock

```php

```

## socket_set_option

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_set_option($socket, SOL_SOCKET, SO_DEBUG, 0));                                  // bool(true)
var_dump(socket_set_option($socket, SOL_SOCKET, SO_KEEPALIVE, 0));                              // bool(true)
var_dump(socket_set_option($socket, SOL_SOCKET, SO_LINGER, ['l_onoff' => 0, 'l_linger' => 0])); // bool(true)

```

## socket_setopt

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_setopt($socket, SOL_SOCKET, SO_DEBUG, 0));                                  // bool(true)
var_dump(socket_setopt($socket, SOL_SOCKET, SO_KEEPALIVE, 0));                              // bool(true)
var_dump(socket_setopt($socket, SOL_SOCKET, SO_LINGER, ['l_onoff' => 0, 'l_linger' => 0])); // bool(true)

```

## socket_shutdown

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.2');
socket_connect($socket, '127.0.0.1', 80);
var_dump(socket_shutdown($socket));    // bool(true)
var_dump(socket_shutdown($socket, 0)); // bool(true)
var_dump(socket_shutdown($socket, 1)); // bool(true)
var_dump(socket_shutdown($socket, 2)); // bool(true)

```

## socket_strerror

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_strerror(socket_last_error()));

```

## socket_write

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.2');
socket_connect($socket, '127.0.0.1', 80);
var_dump(socket_write($socket, 'GET / HTTP/1.1' . "\r\n" . 'Host: www.example.com')); // int(37)

```

## socket_wsaprotocol_info_export

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_wsaprotocol_info_export($socket, getmypid()));

```

## socket_wsaprotocol_info_import

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_wsaprotocol_info_import(socket_wsaprotocol_info_export($socket, getmypid()))); // resource(5) of type (Socket)

```

## socket_wsaprotocol_info_release

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_wsaprotocol_info_release(socket_wsaprotocol_info_export($socket, getmypid()))); // bool(true)

```

