# return

如果在一个函数中调用 `return` 语句，将立即结束此函数的执行并将它的参数作为函数的值返回。

```php
<?php

/**
 * Return an integer.
 *
 * @param  void
 * @return int
 */
function foo(): int
{
    return 5;
}

var_dump(foo()); // int(5)

```

如果在全局范围中调用，则当前脚本文件中止运行。如果当前脚本文件是被 `require` 的或者 `include` 的，则控制交回调用文件。此外，如果当前脚本是被 `require` 的或者 `include` 的，则 `return` 的值会被当作 `require` 或 `include` 调用的返回值。如果在主脚本文件中调用 `return` ，则脚本中止运行。

```php
<?php

$foo = require __DIR__ . '/example.php';
var_dump($foo); // string(3) "foo"

```

上例中的 `example.php` 文件内容：

```php
<?php

$foo = 'foo';
return $foo;

```

