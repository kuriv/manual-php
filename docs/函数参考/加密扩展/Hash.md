# Hash

* [hash_algos - 返回已注册的哈希算法列表](#hashalgos)
* [hash_copy - 拷贝哈希运算上下文](#hashcopy)
* [hash_equals - 防止时序攻击的哈希字符串比较](#hashequals)
* [hash_file - 使用指定的哈希算法给指定的文件的内容生成哈希值](#hashfile)
* [hash_final - 结束增量哈希，并且返回摘要结果](#hashfinal)
* [hash_hkdf - 生成提供的密钥输入的 HKDF 密钥派生](#hashhkdf)
* [hash_hmac_algos - 返回适用于 HMAC 方法的已注册的哈希算法列表](#hashhmacalgos)
* [hash_hmac_file - 使用 HMAC 方法和给定文件的内容生成带密钥的哈希值](#hashhmacfile)
* [hash_hmac - 使用 HMAC 方法生成带有密钥的哈希值](#hashhmac)
* [hash_init - 初始化增量哈希运算上下文](#hashinit)
* [hash_pbkdf2 - 生成所提供密码的 PBKDF2 密钥导出](#hashpbkdf2)
* [hash_update_file - 从文件向活跃的哈希运算上下文中填充数据](#hashupdatefile)
* [hash_update_stream - 从打开的流向活跃的哈希运算上下文中填充数据](#hashupdatestream)
* [hash_update - 向活跃的哈希运算上下文中填充数据](#hashupdate)
* [hash - 生成哈希值](#hash)

## hash_algos

```php
<?php

var_dump(hash_algos());

```

## hash_copy

```php
<?php

$context = hash_init('md5');
var_dump(hash_copy($context));

```

## hash_equals

```php
<?php

var_dump(hash_equals(hash('md5', 'password'), hash('md5', 'password')));       // bool(true)
var_dump(hash_equals(hash('sha256', 'password'), hash('sha256', 'password'))); // bool(true)
var_dump(hash_equals(hash('sha256', 'password'), hash('sha256', 'test')));     // bool(false)

```

## hash_file

```php
<?php

var_dump(hash_file('md5', __DIR__ . '/example.txt'));
var_dump(hash_file('sha256', __DIR__ . '/example.txt'));

```

## hash_final

```php
<?php

$context = hash_init('md5');
hash_update($context, 'foo');
var_dump(hash_final($context)); // string(32) "acbd18db4cc2f85cedef654fccc4a4d8"

```

## hash_hkdf

```php
<?php

var_dump(hash_hkdf('sha256', random_bytes(32), 32, 'aes-256-encryption', random_bytes(16)));

```

## hash_hmac_algos

```php
<?php

var_dump(hash_hmac_algos());

```

## hash_hmac_file

```php
<?php

var_dump(hash_hmac_file('sha256', __DIR__ . '/example.txt', '._._._'));

```

## hash_hmac

```php
<?php

var_dump(hash_hmac('sha256', 'foo', '._._._')); // string(64) "60436878fe4a16fa3a3cd9f14f3c21971011f5f3cefaac64fe2a3f47ff82a6e8"

```

## hash_init

```php
<?php

var_dump(hash_init('md5'));
var_dump(hash_init('sha256'));

```

## hash_pbkdf2

```php
<?php

$algo = 'sha256';
$password = 'password';
$salt = openssl_random_pseudo_bytes(16);
$iterations = 1000;
var_dump(hash_pbkdf2($algo, $password, $salt, $iterations));
var_dump(hash_pbkdf2($algo, $password, $salt, $iterations, 0));
var_dump(hash_pbkdf2($algo, $password, $salt, $iterations, 20));

```

## hash_update_file

```php
<?php

$context = hash_init('md5');
hash_update_file($context, __DIR__ . '/example.txt');
var_dump(hash_final($context));

```

## hash_update_stream

```php
<?php

$context = hash_init('md5');
$handle = fopen(__DIR__ . '/example.txt', 'r');
hash_update_stream($context, $handle);
var_dump(hash_final($context));

```

## hash_update

```php
<?php

$context = hash_init('md5');
hash_update($context, 'foo');
var_dump(hash_final($context)); // string(32) "acbd18db4cc2f85cedef654fccc4a4d8"

```

## hash

```php
<?php

var_dump(hash('md5', 'password'));    // string(32) "5f4dcc3b5aa765d61d8327deb882cf99"
var_dump(hash('sha256', 'password')); // string(64) "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8"

```

