# declare

Tick （时钟周期）是一个在 `declare` 代码段中解释器每执行 N 条可计时的低级语句就会发生的事件。 N 的值是在 `declare` 中用 `ticks = N` 来指定的。不是所有语句都可计时。通常条件表达式和参数表达式都不可计时。在每个 Tick 中出现的事件是由 `register_tick_function()` 来指定的。注意每个 Tick 中可以出现多个事件。

```php
<?php

declare(ticks = 1);

/**
 * Just a test function.
 *
 * @param  void
 * @return void
 */
function foo()
{
    var_dump('foo');
}

register_tick_function('foo');
$foo = 1;
if ($foo > 0) {
    $foo += 2;
}
// string(3) "foo"
// string(3) "foo"
// string(3) "foo"

```

默认情况下，如果能做到的话， PHP 将会强迫错误类型的值转为函数期望的标量类型。 例如，一个函数的一个参数期望是字符串，但传入的是整型，最终函数得到的将会是一个字符串类型的值。可以基于每一个文件开启严格模式。在严格模式中，只有一个与类型声明完全相符的变量才会被接受，否则将会抛出一个 `TypeError` 。 唯一的一个例外是可以将整型传给一个期望浮点数的函数。使用 `declare` 语句和 `strict_types` 声明来启用严格模式。启用严格模式同时也会影响返回值类型声明。严格类型适用于在启用严格模式的文件内的函数调用，而不是在那个文件内声明的函数。 一个没有启用严格模式的文件内调用了一个在启用严格模式的文件中定义的函数，那么将会遵循调用者的偏好（弱类型），而这个值将会被转换。

```php
<?php

declare(strict_types = 1);

$foo = print_r('foo', 1);
// PHP Fatal error:  Uncaught TypeError: print_r() expects parameter 2 to be bool, int given.

```

