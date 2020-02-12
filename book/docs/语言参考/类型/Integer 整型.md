# Integer 整型

整型值可以使用十进制，十六进制，八进制或二进制表示，前面可以加上可选的符号 - 或者 + 。要使用十六进制表达，数字前必须加上 `0x` 。要使用八进制表达，数字前必须加上 `0` 。要使用二进制表达，数字前必须加上 `0b` 。

```php
<?php

$foo = -10;
$bar = 0x1A;
$baz = 010;
$qux = 0b11111111;

```

转换为整型：

```php
<?php

var_dump((int) -42);       // int(-42)
var_dump((int) 42);        // int(42)
var_dump((int) 0.0001);    // int(0)
var_dump((int) 4.2);       // int(4)
var_dump((int) '+42');     // int(42)
var_dump((int) '-42');     // int(-42)
var_dump((int) 1e7);       // int(10000000)
var_dump((int) '1e7');     // int(10000000)
var_dump((int) 0b11);      // int(3)
var_dump((int) '0b11');    // int(0)
var_dump((int) 042);       // int(34)
var_dump((int) '042');     // int(42)
var_dump((int) 0x99);      // int(153)
var_dump((int) '0x99');    // int(0)
var_dump((int) []);        // int(0)
var_dump((int) [0, 1, 2]); // int(1)

```

注意，绝不要将未知的浮点型值强制转换为整型值，这样会导致不可预料的结果。

```php
<?php

var_dump((int) ((0.1 + 0.7) * 10)); // int(7)

```

这是因为以十进制能够精确表示的有理数如 `0.1` 或 `0.7` ，无论有多少尾数都不能被内部所使用的二进制精确表示，因此不能在不丢失一点精度的情况下转换为二进制的格式。

```php
<?php

printf('%0.16f', 0.1 + 0.7); // 0.7999999999999999

```

