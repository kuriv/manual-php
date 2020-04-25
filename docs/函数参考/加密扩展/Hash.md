# Hash

* [hash_algos - 返回已注册的哈希算法列表]
* [hash_copy - 拷贝哈希运算上下文]
* [hash_equals - 防止时序攻击的字符串比较]
* [hash_file - 使用指定的哈希算法给指定的文件的内容生成哈希值]
* [hash_final - 结束增量哈希，并且返回摘要结果]

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













## hash_init

```php
<?php

var_dump(hash_init('md5'));
var_dump(hash_init('sha256'));

```





