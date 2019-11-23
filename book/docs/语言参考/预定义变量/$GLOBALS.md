# $GLOBALS

`$GLOBALS` 是一个包含了全部变量的全局组合数组。变量的名字就是数组的键。

```php
<?php

/**
 * Use superglobal variables in function.
 *
 * @param  void
 * @return string
 */
function foo(): string
{
    return $GLOBALS['foo'];
}

$foo = 'foo';
var_dump(foo()); // string(3) "foo"

```

