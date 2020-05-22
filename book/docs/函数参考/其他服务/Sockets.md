# Sockets

* [socket_accept - 接受套接字上的连接](#socketaccept)
* [socket_addrinfo_bind - 从给定的主机名创建并绑定到套接字](#socketaddrinfobind)
* [socket_addrinfo_connect - 从给定的主机名创建并连接到套接字](#socketaddrinfoconnect)
* [socket_addrinfo_explain - 获取有关的主机名的信息](#socketaddrinfoexplain)
* [socket_addrinfo_lookup - 获取包含有关给定主机名的内容的数组](#socketaddrinfolookup)
* [socket_bind - 给套接字绑定名字](#socketbind)
* [socket_clear_error - 清除套接字或者最后的错误代码上的错误](#socketclearerror)
* [socket_close - 关闭套接字资源](#socketclose)
* [socket_connect - 开启一个套接字连接](#socketconnect)
* [socket_create_listen - 打开端口上的套接字以接受连接](#socketcreatelisten)
* [socket_create_pair - 创建一对不可区分的套接字，并将它们存储在数组中](#socketcreatepair)
* [socket_create - 创建一个套接字（通讯节点）](#socketcreate)
* [socket_export_stream - 将套接字扩展资源导出到封装套接字的流中](#socketexportstream)
* [socket_get_option - 获取套接字的套接字选项](#socketgetoption)
* [socket_getopt - 获取套接字的套接字选项](#socketgetopt)
* [socket_getpeername - 查询给定套接字的远程端](#socketgetpeername)
* [socket_getsockname - 查询给定套接字的本地端](#socketgetsockname)
* [socket_import_stream - 导入流](#socketimportstream)
* [socket_last_error - 返回套接字上的最后一个错误](#socketlasterror)
* [socket_listen - 侦听套接字上的连接](#socketlisten)
* [socket_read - 从套接字读取最大长度的字节](#socketread)
* [socket_recv - 从已连接的套接字接收数据](#socketrecv)
* [socket_recvfrom - 从套接字接收数据，无论它是否连接](#socketrecvfrom)
* [socket_select - 在给定的套接字数组上以指定的超时时间运行 select 系统调用](#socketselect)
* [socket_send - 将数据发送到连接的套接字](#socketsend)
* [socket_sendto - 向套接字发送消息，无论是否已连接](#socketsendto)
* [socket_set_block - 在套接字资源上设置阻塞模式](#socketsetblock)
* [socket_set_nonblock - 在套接字资源上设置非阻塞模式](#socketsetnonblock)
* [socket_set_option - 设置套接字的套接字选项](#socketsetoption)
* [socket_setopt - 设置套接字的套接字选项](#socketsetopt)
* [socket_shutdown - 关闭用于接收，发送或同时接收和接收的套接字](#socketshutdown)
* [socket_strerror - 返回描述套接字错误的字符串](#socketstrerror)
* [socket_write - 写入套接字](#socketwrite)
* [socket_wsaprotocol_info_export - 导出 WSAPROTOCOL_INFO 结构](#socketwsaprotocolinfoexport)
* [socket_wsaprotocol_info_import - 从另一个进程导入套接字](#socketwsaprotocolinfoimport)
* [socket_wsaprotocol_info_release - 释放导出的 WSAPROTOCOL_INFO 结构](#socketwsaprotocolinforelease)

## socket_accept

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.1', 8080);
socket_listen($socket);
while (true) {
    var_dump(socket_accept($socket));
}

```

## socket_addrinfo_bind

```php
<?php

var_dump(socket_addrinfo_bind((socket_addrinfo_lookup('127.0.0.1'))[0])); // resource(5) of type (Socket)

```

## socket_addrinfo_connect

```php
<?php

var_dump(socket_addrinfo_connect((socket_addrinfo_lookup('127.0.0.1'))[0]));

```

## socket_addrinfo_explain

```php
<?php

var_dump(socket_addrinfo_explain((socket_addrinfo_lookup('127.0.0.1'))[0]));

```

## socket_addrinfo_lookup

```php
<?php

var_dump(socket_addrinfo_lookup('127.0.0.1')); // array(1) { [0]=> resource(1) of type (AddressInfo) }

```

## socket_bind

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_bind($socket, '127.0.0.1', 8080)); // bool(true)

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
var_dump(socket_connect($socket, '127.0.0.1', 8080)); // bool(true)

```

## socket_create_listen

```php
<?php

var_dump(socket_create_listen(8080)); // resource(4) of type (Socket)

```

## socket_create_pair

```php
<?php

var_dump(socket_create_pair(AF_INET, SOCK_STREAM, SOL_TCP, $fd)); // bool(true)
var_dump($fd);                                                    // array(2) { [0]=> resource(1) of type (Socket) [1]=> resource(2) of type (Socket) }

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
<?php

var_dump(socket_export_stream(socket_create(AF_INET, SOCK_STREAM, SOL_TCP))); // resource(5) of type (stream)

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
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_connect($socket, '127.0.0.1', 8080);
var_dump(socket_getpeername($socket, $address)); // bool(true)
var_dump($address);                              // string(9) "127.0.0.1"

```

## socket_getsockname

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_connect($socket, '127.0.0.1', 8080);
var_dump(socket_getsockname($socket, $address)); // bool(true)
var_dump($address);                              // string(9) "127.0.0.1"

```

## socket_import_stream

```php
<?php

var_dump(socket_import_stream(stream_socket_server('tcp://127.0.0.1:8080'))); // resource(6) of type (Socket)

```

## socket_last_error

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_last_error()); // int(0)

```

## socket_listen

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.1', 8080);
var_dump(socket_listen($socket)); // bool(true)

```

## socket_read

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.1', 8080);
socket_listen($socket);
while (true) {
    if (($resource = socket_accept($socket)) !== false) {
        var_dump(socket_read($resource, 1024));
    }
}

```

## socket_recv

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.1', 8080);
socket_listen($socket);
while (true) {
    if (($resource = socket_accept($socket)) !== false) {
        var_dump(socket_recv($resource, $buf, 1024, MSG_OOB));
        var_dump($buf);
    }
}

```

## socket_recvfrom

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_bind($socket, '127.0.0.1', 8080);
socket_listen($socket);
while (true) {
    if (($resource = socket_accept($socket)) !== false) {
        var_dump(socket_recvfrom($resource, $buf, 1024, MSG_OOB, $name, $port));
        var_dump($buf, $name, $port);
    }
}

```

## socket_select

```php
<?php

var_dump(socket_select($read, $write, $except, 0));

```

## socket_send

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_connect($socket, '127.0.0.1', 8080);
var_dump(socket_send($socket, 'foo', 3, MSG_OOB)); // int(3)

```

## socket_sendto

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
socket_connect($socket, '127.0.0.1', 8080);
var_dump(socket_sendto($socket, 'foo', 3, MSG_OOB, '127.0.0.1', 8080)); // int(3)

```

## socket_set_block

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_set_block($socket)); // bool(true)

```

## socket_set_nonblock

```php
<?php

$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
var_dump(socket_set_nonblock($socket)); // bool(true)

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
socket_connect($socket, '127.0.0.1', 8080);
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
socket_connect($socket, '127.0.0.1', 8080);
var_dump(socket_write($socket, 'foo')); // int(3)

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

