# goto

`goto` 操作符可以用来跳转到程序中的另一位置。该目标位置可以用目标名称加上冒号来标记，而跳转指令是 `goto` 之后接上目标位置的标记。 PHP 中的 `goto` 有一定限制，目标位置只能位于同一个文件和作用域，也就是说无法跳出一个函数或类方法，也无法跳入到另一个函数。也无法跳入到任何循环或者 `switch` 结构中。

```php
<?php

goto bar;
var_dump('foo');

bar:
var_dump('bar');
// string(3) "bar"

```

可以跳出循环或者 `switch` ，通常的用法是用 `goto` 代替多层的 `break` 。

```php
<?php

for ($i = 0; $i < 10; $i++) {
    if ($i == 5) {
        goto foo;
    }
}

foo:
var_dump('foo');
// string(3) "foo"

```

