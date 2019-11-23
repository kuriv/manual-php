# do-while

`do-while` 循环和 `while` 循环非常相似，区别在于表达式的值是在每次循环结束时检查而不是开始时。

```php
<?php

$foo = 1;
do {
    $foo++;
} while ($foo < 10);

```

和一般的 `while` 循环主要的区别是 `do-while` 的循环语句保证会执行一次（表达式的真值在每次循环结束后检查），然而在一般的 `while` 循环中就不一定了（表达式真值在循环开始时检查，如果一开始就为 `false` 则整个循环立即终止）。

```php
<?php

do {
    $foo = 'foo';
} while (false);
var_dump($foo); // string(3) "foo"

```

