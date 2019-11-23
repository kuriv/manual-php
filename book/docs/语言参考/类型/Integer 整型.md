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

