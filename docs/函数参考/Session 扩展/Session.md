# Session

* [session_abort - 放弃会话数组的修改并结束会话](#sessionabort)
* [session_cache_expire - 返回当前缓存的到期时间](#sessioncacheexpire)
* [session_cache_limiter - 读取 / 设置缓存限制器](#sessioncachelimiter)
* [session_commit - 写入会话数据并结束会话](#sessioncommit)
* [session_create_id - 创建新的会话 ID](#sessioncreateid)
* [session_decode - 解码会话数据](#sessiondecode)
* [session_destroy - 销毁一个会话中的全部数据](#sessiondestroy)
* [session_encode - 将当前会话数据编码为一个字符串](#sessionencode)
* [session_gc - 执行会话数据垃圾回收](#sessiongc)
* [session_get_cookie_params - 获取会话 Cookie 参数](#sessiongetcookieparams)
* [session_id - 获取 / 设置当前会话 ID](#sessionid)
* [session_module_name - 获取 / 设置会话模块名称](#sessionmodulename)
* [session_name - 读取 / 设置会话名称](#sessionname)
* [session_regenerate_id - 使用新生成的会话 ID 更新现有会话 ID](#sessionregenerateid)
* [session_register_shutdown - 关闭会话](#sessionregistershutdown)
* [session_reset - 使用原始值重新初始化会话数组](#sessionreset)
* [session_save_path - 读取 / 设置当前会话的保存路径](#sessionsavepath)
* [session_set_cookie_params - 设置会话 Cookie 参数](#sessionsetcookieparams)
* [session_set_save_handler - 设置用户自定义会话存储函数](#sessionsetsavehandler)
* [session_start - 启动新会话或者重用现有会话](#sessionstart)
* [session_status - 返回当前会话状态](#sessionstatus)
* [session_unset - 释放所有的会话变量](#sessionunset)
* [session_write_close - 写入会话数据并结束会话](#sessionwriteclose)

## session_abort

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
session_commit();

session_start();
$_SESSION['foo'] = 'bar';
session_abort();

session_start();
var_dump($_SESSION['foo']); // string(3) "foo"

```

## session_cache_expire

```php
<?php

var_dump(session_cache_expire(60));  // int(180)
var_dump(session_cache_expire());    // int(60)

```

## session_cache_limiter

```php
<?php

var_dump(session_cache_limiter('private')); // string(7) "nocache"
var_dump(session_cache_limiter());          // string(7) "private"

```

## session_commit

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
$_SESSION['bar'] = 'bar';
var_dump(session_commit()); // bool(true)

```

## session_create_id

```php
<?php

var_dump(session_create_id());
var_dump(session_create_id('prefix-'));

```

## session_decode

```php
<?php

session_start();
var_dump(session_decode('foo|s:3:"foo";bar|s:3:"bar";')); // bool(true)
var_dump($_SESSION['foo']);                               // string(3) "foo"
var_dump($_SESSION['bar']);                               // string(3) "bar"

```

## session_destory

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
$_SESSION['bar'] = 'bar';
session_commit();

session_start();
var_dump($_SESSION['foo']);  // string(3) "foo"
var_dump($_SESSION['bar']);  // string(3) "bar"
var_dump(session_destroy()); // bool(true)
var_dump($_SESSION['foo']);  // string(3) "foo"
var_dump($_SESSION['bar']);  // string(3) "bar"

```

## session_encode

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
$_SESSION['bar'] = 'bar';
var_dump(session_encode()); // string(28) "foo|s:3:"foo";bar|s:3:"bar";"

```

## session_gc

```php
<?php

session_start();
var_dump(session_gc());

```

## session_get_cookie_params

```php
<?php

var_dump(session_get_cookie_params());

```

## session_id

```php
<?php

var_dump(session_id(session_create_id()));
var_dump(session_id());

```

## session_module_name

```php
<?php

var_dump(session_module_name('files')); // string(5) "files"
var_dump(session_module_name());        // string(5) "files"

```

## session_name

```php
<?php

var_dump(session_name('PHPSESSID')); // string(9) "PHPSESSID"
var_dump(session_name());            // string(9) "PHPSESSID"

```

## session_regenerate_id

```php
<?php

session_start();
var_dump(session_regenerate_id());     // bool(true)
var_dump(session_regenerate_id(true)); // bool(true)

```

## session_register_shutdown

```php
<?php

var_dump(session_register_shutdown());

```

## session_reset

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
session_commit();

session_start();
$_SESSION['foo'] = 'bar';
session_reset();
var_dump($_SESSION['foo']); // string(3) "foo"

```

## session_save_path

```php
<?php

var_dump(session_save_path(__DIR__));
var_dump(session_save_path());

```

## session_set_cookie_params

```php
<?php

var_dump(session_set_cookie_params(3600, '/', '.github.com', true, true)); // bool(true)

```

## session_set_save_handler

```php
<?php

$handle = new SessionHandler();
var_dump(session_set_save_handler($handle, true)); // bool(true)

```

## session_start

```php
<?php

var_dump(session_start()); // bool(true)

```

## session_status

```php
<?php

var_dump(session_status());

```

## session_unset

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
$_SESSION['bar'] = 'bar';
session_unset();
var_dump($_SESSION['foo']); // NULL
var_dump($_SESSION['bar']); // NULL

```

## session_write_close

```php
<?php

session_start();
$_SESSION['foo'] = 'foo';
$_SESSION['bar'] = 'bar';
var_dump(session_write_close()); // bool(true)

```

