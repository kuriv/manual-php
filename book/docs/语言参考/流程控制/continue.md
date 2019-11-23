# continue

`continue` 在循环结构中用来跳过本次循环中剩余的代码并在条件求值为真时开始执行下一次循环。它可以接受一个可选的数字参数来决定跳过几重循环到循环结尾。默认值是 1 ，即跳到当前循环末尾。

`continue` 跳过当前 `for` 结构的执行。

```php
<?php

for ($i = 1; $i < 10; $i++) {
    if ($i == 5) {
        continue;
    }
}

```

`continue` 跳过当前 `foreach` 结构的执行。

```php
<?php

$foo = [2, 4, 5];
foreach ($foo as $value) {
    if ($value == 2) {
        continue;
    }
}

```

`continue` 跳过当前 `while` 结构的执行。

```php
<?php

$foo = 1;
while ($foo < 10) {
    $foo++;
    if ($foo == 5) {
        continue;
    }
}

```

`continue` 跳过当前 `do-while` 结构的执行。

```php
<?php

$foo = 1;
do {
    $foo++;
    if ($foo == 5) {
        continue;
    }
} while ($foo < 10);

```

`continue` 跳过当前 `switch` 结构的执行。

```php
<?php

$foo = 1;
while ($foo++ < 10) {
    while (true) {
        while (true) {
            continue 3;
        }
    }
}

```

