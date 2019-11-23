# break

`break` 在循环结构中用来结束当前循环结构的执行。它可以接受一个可选的数字参数来决定跳出几重循环。默认值是 1 ，即结束当前循环结构的执行。

`break` 结束当前 `for` 结构的执行。

```php
<?php

for ($i = 1; $i < 10; $i++) {
    if ($i == 5) {
        break;
    }
}

```

`break` 结束当前 `foreach` 结构的执行。

```php
<?php

$foo = [2, 4, 5];
foreach ($foo as $value) {
    if ($value == 2) {
        break;
    }
}

```

`break` 结束当前 `while` 结构的执行。

```php
<?php

$foo = 1;
while ($foo < 10) {
    if ($foo == 5) {
        break;
    }
    $foo++;
}

```

`break` 结束当前 `do-while` 结构的执行。

```php
<?php

$foo = 1;
do {
    if ($foo == 5) {
        break;
    }
    $foo++;
} while ($foo < 10);

```

`break` 结束当前 `switch` 结构的执行。

```php
<?php

$foo = 1;
while ($foo++) {
    switch ($foo) {
        case 5:
            break 1;
        case 10:
            break 2;
        default:
            break;
    }
}

```

