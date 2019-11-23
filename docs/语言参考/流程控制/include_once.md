# include_once

`include_once` 语句和 `include` 语句完全相同，唯一区别是 PHP 会检查该文件是否已经被包含过，如果是则不会再次包含。 `include_once` 可以用于在脚本执行期间同一个文件有可能被包含超过一次的情况下，想确保它只被包含一次以避免函数重定义，变量重新赋值等问题。

```php
<?php

include_once __DIR__ . '/example.php';

```

