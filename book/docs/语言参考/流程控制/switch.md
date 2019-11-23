# switch

`switch` 语句类似于具有同一个表达式的一系列 `if` 语句。很多场合下需要把同一个变量（或表达式）与很多不同的值比较，并根据它等于哪个值来执行不同的代码。这正是 `switch` 语句的用途。如果比较一个数字和字符串或者比较涉及到数字内容的字符串，则字符串会被转换为数值并且比较按照数值来进行。

```php
<?php

$foo = 'foo';
switch ($foo) {
    case 0:
        var_dump(0);
        break;
    case 'foo':
        var_dump('foo');
        break;
}
// int(0)

```

为避免错误，理解 `switch` 是怎样执行的非常重要。 `switch` 语句一行接一行地执行（实际上是语句接语句）。开始时没有代码被执行。仅当一个 `case` 语句中的值和 `switch` 表达式的值匹配时 PHP 才开始执行语句，直到 `switch` 的程序段结束或者遇到第一个 `break` 语句为止。如果不在 `case` 的语句段最后写上 `break` 的话， PHP 将继续执行下一个 `case` 中的语句段。

```php
<?php

$foo = 'foo';
switch ($foo) {
    case 0:
        var_dump(0);
        // no break
    case 'bar':
        var_dump('bar');
        // no break
}
// int(0)
// string(3) "bar"

```

在一个 `case` 中的语句也可以为空，这样只不过将控制转移到了下一个 `case` 中的语句。

```php
<?php

$foo = 'foo';
switch ($foo) {
    case 0:
    case 'bar':
        var_dump('bar');
        break;
}
// string(3) "bar"

```

一个 `case` 的特例是 `default` 。它匹配了任何和其它 `case` 都不匹配的情况。

```php
<?php

$foo = 5;
switch ($foo) {
    case 1:
        var_dump(1);
        break;
    case 2:
        var_dump(2);
        break;
    default:
        var_dump($foo);
        break;
}
// int(5)

```

