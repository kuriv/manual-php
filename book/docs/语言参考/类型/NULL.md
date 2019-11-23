# NULL

特殊的 `NULL` 类型表示一个变量没有值。 `NULL` 类型唯一可能的值就是 `NULL` 。

在下列情况下一个变量被认为是 `NULL` ：

* 尚未被赋值。
* 被赋值为 `NULL` 。
* 被 `unset()` 。

```php
<?php

$foo;
$foo = null;
unset($foo);

```

