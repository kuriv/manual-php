# foreach

`foreach` 语法结构提供了遍历数组的简单方式。 `foreach` 仅能够应用于数组和对象，如果尝试应用于其他数据类型的变量，或者未初始化的变量将发出错误信息。第一种格式遍历给定的数组。每次循环中，当前单元的值被赋给 `$value` 并且数组内部的指针向前移一步（因此下一次循环中将会得到下一个单元）。

```php
<?php

$foo = [2, 4, 5];
foreach ($foo as $value) {
}

```

第二种格式做同样的事，只除了当前单元的键名也会在每次循环中被赋给变量 `$key` 。

```php
<?php

$foo = [2, 4, 5];
foreach ($foo as $key => $value) {
}

```

可以通过引用来修改数组的元素。

```php
<?php

$foo = [2, 4, 5];
foreach ($foo as &$value) {
    $value += 1;
}
unset($value);
var_dump($foo); // array(3) { [0]=> int(3) [1]=> int(5) [2]=> int(6) }

```

还可以通过嵌套 `foreach` 语法结构来遍历多维数组。

```php
<?php

$foo = [[2], [4], [5]];
foreach ($foo as $value) {
    foreach ($value as $v) {
    }
}

```

PHP 可以遍历一个数组的并且把多维数组解包到循环变量中，只需将 `list()` 作为值提供。

```php
<?php

$foo = [['foo', 'bar'], ['baz', 'qux']];
foreach ($foo as list($a, $b)) {
}

```

